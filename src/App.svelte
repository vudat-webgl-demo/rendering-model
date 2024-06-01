<script>
  import * as THREE from "../build/three.module";
  import { onMount, tick } from "svelte";
  import { GLTFLoader } from "../js/GLTFLoader";
  import { OrbitControls } from "../js/OrbitControls";
  import { TWEEN } from "../js/tween.module.min.js";
  import { EXRLoader } from "../js/EXRLoader.js";
  import { environments } from "../src/assets/environment/index.js";
  import { RoomEnvironment } from "../js/RoomEnvironment.js";
  import { sRGBEncoding } from "../build/three.module";
  import { EffectComposer } from "../js/post-processing/EffectComposer.js";
  import { RenderPass } from "../js/RenderPass.js";
  import { GTAOPass } from "../js/post-processing/GTAOPass.js";
  import { OutputPass } from "../js/post-processing/OutputPass.js";
  import { ReflectorForSSRPass } from "../js/post-processing/ReflectorForSSRPass.js";
  import { SSRPass } from "../js/post-processing/SSRPass.js";
  import { GammaCorrectionShader } from "../js/shaders/GammaCorrectionShader.js";

  import { LuminosityShader } from "../js/shaders/LuminosityShader.js";

  import { ShaderPass } from "../js/post-processing/ShaderPass.js";
  import { ACESFilmicToneMappingShader } from "../js/shaders/ACESFilmicToneMappingShader.js";
  import { CopyShader } from "../js/shaders/CopyShader.js";

  // import { GUI } from "../build/dat.gui.module.js";
  import { GUI } from "../js/lil-gui.module.min.js";

  let canvas, renderer;
  let controls;
  let loader;
  let scene;
  let camera;
  let clock;
  let motobike;
  let composer;
  let raycaster = new THREE.Raycaster(); //
  let mouse = new THREE.Vector2();
  let helper;
  let iron;
  let exrEnv;
  let startTime, endTime;
  startTime = new Date();
  let selectedObjects = [];
  let isGoMallMode = false;
  let pmremGenerator;
  let neutralEnvironment;
  let cubeRenderTarget;
  let cubeCamera;
  const ssrParams = {
    enableSSR: true,
    autoRotate: true,
    otherMeshes: true,
    groundReflector: true,
  };

  let ssrPass;
  const otherMeshes = [];
  let groundReflector;
  const selects = [];
  let initialState = {
    environment: "Forest",
    background: false,
  };
  let pmremCubeRenderTarget;
  let internalEnvMap;
  $: console.log("selectedObjects: ", selectedObjects);
  const widthScreen = window.innerWidth;
  const heightScreen = window.innerHeight; //
  const SHADOW_MAP_WIDTH = 2048,
    SHADOW_MAP_HEIGHT = 1024;
  const vanElement = [
    "Color_M00168",
    "Color_M00158",
    "Color_M00136",
    "Color_M00181",
    "Color_M00197",
    "Default_150150150008",
    "Color_M00210",
    "Color_M00173",
    "Color_M00176",
    "Color_M00127",
    "Color_M00426",
    "Default_150150150004",
    "Color_M00169",
    "Color_M00170",
    "Color_M00149",
    "Color_M00135",
    "Color_M00426",
    "Color_M00381",
  ];
  const init = () => {
    let path = "src/assets/cube-screen/";
    let format = ".jpg";
    let urls = [
      path + "pano_r" + format,
      path + "pano_l" + format,
      path + "pano_u" + format,
      path + "pano_d" + format,
      path + "pano_f" + format,

      path + "pano_b" + format,
    ];
    camera = new THREE.PerspectiveCamera(
      60,
      widthScreen / heightScreen,
      0.1,
      100
    );
    camera.position.set(3, 2, 3);
    // camera = new THREE.PerspectiveCamera(
    //   60,
    //   widthScreen / heightScreen,
    //   0.001,
    //   10000
    // );
    // camera.position.set(0, 0, 0);
    scene = new THREE.Scene();
    scene.background = new THREE.Color(0xcccccc);

    clock = new THREE.Clock();
    const Camhelper = new THREE.CameraHelper(camera);
    // scene.add(Camhelper);

    // scene.background = reflectionCube;
    // scene.background = new THREE.Color(0xc2c2c2);
    scene.add(camera);
    const light1 = new THREE.AmbientLight(0xffffff, 0.3);
    // light1.castShadow = true;
    light1.name = "ambient_light";

    scene.add(light1);

    const light = new THREE.DirectionalLight(0xffffff, 0.8 * Math.PI);
    light.castShadow = true;
    // light.shadow.bias = 0.0001;
    // light.position.set(0.5 * 2, 1 * 2, 0.866 * 2); // ~60º
    light.shadow.camera.top = 2000;
    light.shadow.camera.bottom = -2000;
    light.shadow.camera.left = -2000;
    light.shadow.camera.right = 2000;
    light.shadow.camera.near = 1200;
    light.shadow.camera.far = 2500;
    light.shadow.bias = 0.0001;

    light.shadow.mapSize.width = SHADOW_MAP_WIDTH;
    light.shadow.mapSize.height = SHADOW_MAP_HEIGHT;
    scene.add(light);

    // const hemiLight = new THREE.HemisphereLight();

    // scene.add(hemiLight);
    renderer = new THREE.WebGLRenderer({ canvas });

    renderer.physicallyCorrectLights = true;
    renderer.outputEncoding = sRGBEncoding;

    renderer.setClearColor(0xcccccc);
    renderer.setPixelRatio(window.devicePixelRatio);
    renderer.setSize(widthScreen, heightScreen);
    renderer.toneMapping = THREE.ACESFilmicToneMapping;
    renderer.toneMappingExposure = Math.pow(2, 0);
    renderer.shadowMap.enabled = true;
    renderer.shadowMap.type = THREE.PCFShadowMap;

    cubeRenderTarget = new THREE.WebGLCubeRenderTarget(1024, {
      format: THREE.RGBAFormat,
      generateMipmaps: true,
      minFilter: THREE.LinearMipmapLinearFilter,
      encoding: THREE.sRGBEncoding,
    });

    cubeCamera = new THREE.CubeCamera(1, 10000, cubeRenderTarget);
    cubeCamera.scale.set(0.1, 0.1, 0.1);
    cubeCamera.position.set(-0.3, 0.65, 0);

    const geometry = new THREE.BoxGeometry(1, 1, 1);
    const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
    const cube = new THREE.Mesh(geometry, material);
    cube.position.set(-0.3, 0.65, 0);
    // scene.add(cube);

    // const planeGeometry = new THREE.PlaneGeometry(25, 25);
    // const texture = new THREE.TextureLoader().load(
    //   "src/images/tri_pattern.jpg"
    // );
    // const plane = new THREE.Mesh(
    //   planeGeometry,
    //   new THREE.MeshPhongMaterial({ map: texture })
    // );
    // plane.rotateX(-Math.PI / 2);
    // plane.receiveShadow = true;

    // scene.add(plane);

    let geometryV2 = new THREE.PlaneGeometry(25, 25);
    groundReflector = new ReflectorForSSRPass(geometryV2, {
      clipBias: 0.0003,
      textureWidth: window.innerWidth,
      textureHeight: window.innerHeight,
      color: 0x888888,
      useDepthTexture: true,
    });
    groundReflector.material.depthWrite = false;
    groundReflector.rotation.x = -Math.PI / 2;
    groundReflector.visible = false;
    // scene.add(groundReflector);

    cubeCamera.update(renderer, scene);

    pmremGenerator = new THREE.PMREMGenerator(renderer);
    pmremGenerator.compileEquirectangularShader();

    pmremCubeRenderTarget = pmremGenerator.fromEquirectangular(
      cubeRenderTarget.texture
    );
    internalEnvMap = pmremCubeRenderTarget?.texture;

    neutralEnvironment = pmremGenerator.fromScene(
      new RoomEnvironment()
    ).texture;

    controls = new OrbitControls(camera, renderer.domElement);
    controls.enabled = true;
    // controls.maxPolarAngle = 1.0;
    // controls.minPolarAngle = -0.5;
    // controls.enableDamping = true;
    // controls.screenSpacePanning = true;

    composer = new EffectComposer(renderer);

    const renderPass = new RenderPass(scene, camera);
    composer.addPass(renderPass);

    const gtaoPass = new GTAOPass(scene, camera, widthScreen, heightScreen);
    gtaoPass.output = GTAOPass.OUTPUT.Denoise;
    composer.addPass(gtaoPass);

    ssrPass = new SSRPass({
      renderer,
      scene,
      camera,
      width: widthScreen,
      height: heightScreen,
      groundReflector: ssrParams.groundReflector ? groundReflector : null,
      selects: ssrParams.groundReflector ? selects : null,
    });

    composer.addPass(ssrPass);

    const gammaCorrectionPass = new ShaderPass(GammaCorrectionShader);
    composer.addPass(gammaCorrectionPass);

    // const luminosityPass = new ShaderPass(LuminosityShader);
    // composer.addPass(luminosityPass);
    // Final pass to copy to screen
    // const copyPass = new ShaderPass(CopyShader);
    // copyPass.renderToScreen = true;
    // composer.addPass(copyPass);

    // const ACESFilmicPass = new ShaderPass(ACESFilmicToneMappingShader);
    // composer.addPass(ACESFilmicPass);

    const outputPass = new OutputPass();
    composer.addPass(outputPass);

    loader = new GLTFLoader();
    //Pointer
    let geometryHelper = new THREE.CircleGeometry(0.3, 10000);
    geometryHelper.translate(0, 0, 0.01);
    const marker = new THREE.TextureLoader().load("src/assets/marker.png");

    let rollOverMaterial = new THREE.MeshBasicMaterial({
      map: marker,
      color: 0x00000,
      flatShading: true,
      transparent: true,
      opacity: 0.7,
    });
    // let rollOverMaterial = new THREE.MeshBasicMaterial( {  color: 0xff0000, flatShading: true, transparent: true, opacity: 0.7 } );

    helper = new THREE.Mesh(geometryHelper, rollOverMaterial);

    loader.load(
      "src/models/van/reality_van.glb",
      function (gltf) {
        motobike = gltf.scene;
        // motobike.position.y = distanceYOfbox / 2;
        // motobike.position.x = -distanceXOfbox / 2;
        // motobike.position.z = distanceZOfbox / 2;
        motobike.scale.set(10, 10, 10);

        scene.add(motobike);

        gltf.scene.traverse(function (child) {
          if (child.isMesh) {
            child.castShadow = true;
            child.receiveShadow = true;

            // child.material.envMap = cubeRenderTarget.texture;
            for (let i = 0; i < vanElement.length; i++) {
              if (child.name == vanElement[i]) {
                child.material.envMap = exrEnv;
                selects.push(child); //bị rọi

                break;
              } else {
                // selects.push(child);
                selects.push(child);
                otherMeshes.push(child); //Rọi vào đứa khác
                child.material.envMap = cubeRenderTarget.texture;
                if (child.material.map)
                  child.material.map.encoding = sRGBEncoding;
                if (child.material.emissiveMap)
                  child.material.emissiveMap.encoding = sRGBEncoding;
                if (child.material.map || child.material.emissiveMap)
                  child.material.needsUpdate = true;
              }
            }

            if (child.name == "Color_M00135" || child.name == "Color_M00426") {
              child.visible = false;
            }

            const box = new THREE.Box3().setFromObject(scene);
            gtaoPass.setSceneClipBox(box);
            let aoMap;
            if (child.material && child.material.aoMap) {
              aoMap = child.material.aoMap;
            }

            return child;
          }
        });
        cubeCamera.update(renderer, scene);
        // const sceneV2 = gltf.scene || gltf.scenes[0];
        // const clipsV2 = gltf.animations || [];
        // setContent(sceneV2, clipsV2);
        // setContent(plane, "");
      },
      undefined,
      function (error) {
        console.error(error);
      }
    );
    updateEnvironment();

    cubeCamera.update(renderer, scene);

    // Init gui
    const gui = new GUI();

    gui
      .add(gtaoPass, "output", {
        Default: GTAOPass.OUTPUT.Default,
        Diffuse: GTAOPass.OUTPUT.Diffuse,
        "AO Only": GTAOPass.OUTPUT.AO,
        "AO Only + Denoise": GTAOPass.OUTPUT.Denoise,
        Depth: GTAOPass.OUTPUT.Depth,
        Normal: GTAOPass.OUTPUT.Normal,
      })
      .onChange(function (value) {
        gtaoPass.output = value;
      });

    const aoParameters = {
      radius: 0.25,
      distanceExponent: 1,
      thickness: 1,
      scale: 1,
      samples: 16,
      distanceFallOff: 1,
      screenSpaceRadius: false,
    };
    const pdParameters = {
      lumaPhi: 10,
      depthPhi: 2,
      normalPhi: 3,
      radius: 4,
      radiusExponent: 1,
      rings: 2,
      samples: 16,
    };
    gtaoPass.updateGtaoMaterial(aoParameters);
    gtaoPass.updatePdMaterial(pdParameters);
    gui.add(gtaoPass, "blendIntensity").min(0).max(1).step(0.01);
    gui
      .add(aoParameters, "radius")
      .min(0.01)
      .max(1)
      .step(0.01)
      .onChange(() => gtaoPass.updateGtaoMaterial(aoParameters));
    gui
      .add(aoParameters, "distanceExponent")
      .min(1)
      .max(4)
      .step(0.01)
      .onChange(() => gtaoPass.updateGtaoMaterial(aoParameters));
    gui
      .add(aoParameters, "thickness")
      .min(0.01)
      .max(10)
      .step(0.01)
      .onChange(() => gtaoPass.updateGtaoMaterial(aoParameters));
    gui
      .add(aoParameters, "distanceFallOff")
      .min(0)
      .max(1)
      .step(0.01)
      .onChange(() => gtaoPass.updateGtaoMaterial(aoParameters));
    gui
      .add(aoParameters, "scale")
      .min(0.01)
      .max(2.0)
      .step(0.01)
      .onChange(() => gtaoPass.updateGtaoMaterial(aoParameters));
    gui
      .add(aoParameters, "samples")
      .min(2)
      .max(32)
      .step(1)
      .onChange(() => gtaoPass.updateGtaoMaterial(aoParameters));
    gui
      .add(aoParameters, "screenSpaceRadius")
      .onChange(() => gtaoPass.updateGtaoMaterial(aoParameters));
    gui
      .add(pdParameters, "lumaPhi")
      .min(0)
      .max(20)
      .step(0.01)
      .onChange(() => gtaoPass.updatePdMaterial(pdParameters));
    gui
      .add(pdParameters, "depthPhi")
      .min(0.01)
      .max(20)
      .step(0.01)
      .onChange(() => gtaoPass.updatePdMaterial(pdParameters));
    gui
      .add(pdParameters, "normalPhi")
      .min(0.01)
      .max(20)
      .step(0.01)
      .onChange(() => gtaoPass.updatePdMaterial(pdParameters));
    gui
      .add(pdParameters, "radius")
      .min(0)
      .max(32)
      .step(1)
      .onChange(() => gtaoPass.updatePdMaterial(pdParameters));
    gui
      .add(pdParameters, "radiusExponent")
      .min(0.1)
      .max(4)
      .step(0.1)
      .onChange(() => gtaoPass.updatePdMaterial(pdParameters));
    gui
      .add(pdParameters, "rings")
      .min(1)
      .max(16)
      .step(0.125)
      .onChange(() => gtaoPass.updatePdMaterial(pdParameters));
    gui
      .add(pdParameters, "samples")
      .min(2)
      .max(32)
      .step(1)
      .onChange(() => gtaoPass.updatePdMaterial(pdParameters));

    gui.add(ssrParams, "enableSSR").name("Enable SSR");
    gui.add(ssrParams, "groundReflector").onChange(() => {
      if (ssrParams.groundReflector) {
        (ssrPass.groundReflector = groundReflector),
          (ssrPass.selects = selects);
      } else {
        (ssrPass.groundReflector = null), (ssrPass.selects = null);
      }
    });
    ssrPass.thickness = 0.018;
    gui.add(ssrPass, "thickness").min(0).max(0.1).step(0.0001);
    ssrPass.infiniteThick = false;
    gui.add(ssrPass, "infiniteThick");
    gui.add(ssrParams, "autoRotate").onChange(() => {
      controls.enabled = !ssrParams.autoRotate;
    });

    const folder = gui.addFolder("more settings");
    folder.add(ssrPass, "fresnel").onChange(() => {
      groundReflector.fresnel = ssrPass.fresnel;
    });
    folder.add(ssrPass, "distanceAttenuation").onChange(() => {
      groundReflector.distanceAttenuation = ssrPass.distanceAttenuation;
    });
    ssrPass.maxDistance = 0.3;
    groundReflector.maxDistance = ssrPass.maxDistance;
    folder
      .add(ssrPass, "maxDistance")
      .min(0)
      .max(0.5)
      .step(0.001)
      .onChange(() => {
        groundReflector.maxDistance = ssrPass.maxDistance;
      });
    folder.add(ssrParams, "otherMeshes").onChange(() => {
      if (ssrParams.otherMeshes) {
        otherMeshes.forEach((mesh) => (mesh.visible = true));
      } else {
        otherMeshes.forEach((mesh) => (mesh.visible = false));
      }
    });
    folder.add(ssrPass, "bouncing");
    folder
      .add(ssrPass, "output", {
        Default: SSRPass.OUTPUT.Default,
        "SSR Only": SSRPass.OUTPUT.SSR,
        Beauty: SSRPass.OUTPUT.Beauty,
        Depth: SSRPass.OUTPUT.Depth,
        Normal: SSRPass.OUTPUT.Normal,
        Metalness: SSRPass.OUTPUT.Metalness,
      })
      .onChange(function (value) {
        ssrPass.output = value;
      });
    ssrPass.opacity = 0.355;
    groundReflector.opacity = ssrPass.opacity;
    folder
      .add(ssrPass, "opacity")
      .min(0)
      .max(1)
      .onChange(() => {
        groundReflector.opacity = ssrPass.opacity;
      });
    folder.add(ssrPass, "blur");
    // folder.open()
    // gui.close()
    gui.open();
  };

  const updateEnvironment = () => {
    const environment = environments.filter(
      (entry) => entry.name === initialState.environment
    )[0];

    getCubeMapTexture(environment).then(({ envMap }) => {
      // if (
      //   (!envMap || !this.state.background) &&
      //   this.activeCamera === this.defaultCamera
      // ) {
      //   // this.scene.add(this.vignette);
      // } else {
      //   // this.scene.remove(this.vignette);
      // }
      exrEnv = envMap;
      // scene.environment = envMap;
      // scene.background = initialState.background ? envMap : null;
    });
  };

  const setContent = (object, clips) => {
    // clear();

    const box = new THREE.Box3().setFromObject(object);
    const size = box.getSize(new THREE.Vector3()).length();
    const center = box.getCenter(new THREE.Vector3());

    controls.reset();

    object.position.x += object.position.x - center.x;
    object.position.y += object.position.y - center.y;
    object.position.z += object.position.z - center.z;

    controls.maxDistance = size * 10;
    controls.enableDamping = true;
    camera.near = size / 100;
    camera.far = size * 100;
    camera.updateProjectionMatrix();

    camera.position.copy(center);
    camera.position.x += size / 2.0;
    camera.position.y += size / 5.0;
    camera.position.z += size / 2.0;
    camera.lookAt(center);

    // this.setCamera(DEFAULT_CAMERA);

    // this.axesCamera.position.copy(this.defaultCamera.position);
    // this.axesCamera.lookAt(this.axesScene.position);
    // this.axesCamera.near = size / 100;
    // this.axesCamera.far = size * 100;
    // this.axesCamera.updateProjectionMatrix();
    // this.axesCorner.scale.set(size, size, size);

    controls.saveState();
    object.scale.set(1, 1, 1);
    console.log("object pos: ", object);

    scene.add(object);

    // this.content = object;

    // this.state.punctualLights = true;

    // this.content.traverse((node) => {
    //   if (node.isLight) {
    //     this.state.punctualLights = false;
    //   } else if (node.isMesh) {
    //     // TODO(https://github.com/mrdoob/three.js/pull/18235): Clean up.
    //     node.material.depthWrite = !node.material.transparent;
    //   }
    // }
    //})
  };

  const getCubeMapTexture = (environment) => {
    console.log("environ: ", environment);
    const { id, path } = environment;

    // neutral (THREE.RoomEnvironment)
    if (id === "neutral") {
      return Promise.resolve({ envMap: neutralEnvironment });
    }

    // none
    if (id === "") {
      return Promise.resolve({ envMap: null });
    }

    return new Promise((resolve, reject) => {
      new EXRLoader().load(
        path,
        (texture) => {
          const envMap = pmremGenerator.fromEquirectangular(texture).texture;
          pmremGenerator.dispose();
          console.log("envMap: ", envMap);
          resolve({ envMap });
        },
        undefined,
        reject
      );
    });
  };

  const getDetailModel = (event) => {
    console.log("click detail");
    event.preventDefault();
    mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
    mouse.y = -(event.clientY / window.innerHeight) * 2 + 1;
    raycaster.setFromCamera(mouse, camera);
    let intersects = raycaster.intersectObjects(scene.children, true);

    if (intersects.length > 0) {
      let clickObject = intersects[0].object;
      console.log("click Object: ", clickObject);
    }
  };

  const animate = () => {
    requestAnimationFrame(animate);
    controls.update();
    TWEEN.update();

    if (ssrParams.enableSSR) {
      // TODO: groundReflector has full ground info, need use it to solve reflection gaps problem on objects when camera near ground.
      // TODO: the normal and depth info where groundReflector reflected need to be changed.

      // renderer.render(scene, camera);
      composer.render();
    } else {
      renderer.render(scene, camera);
    }
    // renderer.autoClear = false;
    // renderer.clear();

    // camera.layers.set(1);
    // composer.render();

    // renderer.clearDepth();
    // camera.layers.set(0);
    // renderer.render(scene, camera);
  };
  function onWindowResize() {
    const width = window.innerWidth;
    const height = window.innerHeight;
    // camera.aspect = width / height;
    camera.updateProjectionMatrix();

    renderer.setSize(width, height);
    composer.setSize(width, height);
    groundReflector.getRenderTarget().setSize(width, height);
    groundReflector.resolution.set(width, height);
  }

  onMount(() => {
    init();
    animate();

    window.addEventListener("resize", onWindowResize);
  });
</script>

<main>
  <canvas
    class="full-screen"
    id="container"
    bind:this={canvas}
    on:click={getDetailModel}
  >
  </canvas>
</main>

<!-- on:click={moveCamera}
    on:mousedown={startTimer}
    on:click={getNameObject}
    on:zoom={handleZoom} -->

<style>
  .full-screen {
    margin: 0 !important;
    padding: 0 !important;
  }

  .view-button {
    left: 50%;
    position: relative;
    bottom: 20px;
    transform: translate(-50%, -50%);
    z-index: 1000; /* Ensure the button appears on top of the canvas */
  }

  button {
    padding: 10px;
    background-color: var(--focus-color);
    color: white;
    cursor: pointer;
    border: var(--focus-border);

    outline: none;
    overflow: hidden;
    transition: background-color 0.3s; /* Added transition for smooth color change */
  }

  button:hover {
    background-color: #74b9e7;
  }

  .left-content {
    /* height: 100%; */
  }

  .right-content {
    /* height: 100%; */
  }

  .detail-product {
    /* width: 100%;
    position: absolute;
    height: 100%; */
  }
</style>
