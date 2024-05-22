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
  let canvas, renderer;
  let controls;
  let loader;
  let scene;
  let camera;
  let clock;
  let motobike;

  let raycaster = new THREE.Raycaster();
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
  let material1;
  let cubeCamera;
  let pivot2;
  let childVan;
  let cubeRenderTarget2;
  let cubeCamera2;
  let cube;
  let initialState = {
    environment: "Forest",
    background: false,
  };
  $: console.log("selectedObjects: ", selectedObjects);

  const widthScreen = window.innerWidth;
  const heightScreen = window.innerHeight;
  const SHADOW_MAP_WIDTH = 2048,
    SHADOW_MAP_HEIGHT = 1024;
  const vanElement = [
    "Van-Road-Side-Wall-Upper",
    "Van-Front-Upper",
    "Van-Exterior-Road-Side-Top",
    "Van_Roof",
    "group111",
    "group282",
    "group281",
    "group124",
    "group280",
    "group136",
    "panel",
    "panel001",
    "group283",
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
      0.01,
      1000
    );
    camera.position.set(3, 2, 3);

    // camera.position.set(1, 10, 10);

    // camera.lookAt(1, 0, 0);
    scene = new THREE.Scene();

    clock = new THREE.Clock();
    const Camhelper = new THREE.CameraHelper(camera);
    // scene.add(Camhelper);

    // scene.background = reflectionCube;
    // scene.background = new THREE.Color(0xc2c2c2);
    scene.background = new THREE.Color(0x87ceeb);
    const light1 = new THREE.AmbientLight(0xffffff, 0.3);
    light1.name = "ambient_light";
    scene.add(light1);

    const light = new THREE.DirectionalLight(0xffffff, 0.8 * Math.PI);
    light.castShadow = true;
    light.shadow.bias = 0.0001;
    // light.position.set(0.5, 0, 0.866); // ~60º
    // light.name = "main_light";
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
    renderer.toneMapping = THREE.ACESFilmicToneMapping;
    renderer.setSize(widthScreen, heightScreen);
    renderer.shadowMap.enabled = true;
    renderer.shadowMap.type = THREE.PCFShadowMap;

    cubeRenderTarget = new THREE.WebGLCubeRenderTarget(128, {
      generateMipmaps: true,
      minFilter: THREE.LinearMipmapLinearFilter,
    });

    // cubeRenderTarget = new THREE.WebGLCubeRenderTarget(4000, {
    //   format: THREE.RGBAFormat,
    //   generateMipmaps: true,
    //   minFilter: THREE.LinearMipmapLinearFilter,
    //   encoding: THREE.sRGBEncoding,
    // });

    cubeCamera = new THREE.CubeCamera(0.1, 10000, cubeRenderTarget);

    const cubeRenderTarget2 = new THREE.WebGLCubeRenderTarget(1024, {
      format: THREE.RGBAFormat,
      generateMipmaps: true,
      minFilter: THREE.LinearMipmapLinearFilter,
    });
    // cubeRenderTarget2 = new THREE.WebGLCubeRenderTarget(4000, {
    //   format: THREE.RGBAFormat,
    //   generateMipmaps: true,
    //   minFilter: THREE.LinearMipmapLinearFilter,
    //   encoding: THREE.sRGBEncoding,
    // });
    cubeCamera2 = new THREE.CubeCamera(1, 10000, cubeRenderTarget2);
    // cubeCamera = new THREE.CubeCamera(1, 10000, cubeRenderTarget);
    // cubeCamera.update(renderer, scene);
    // scene.add(cubeCamera);
    cubeCamera2.scale.set(0.1, 0.1, 0.1);
    cubeCamera2.position.set(-0.3, 0.65, 0);

    const geometry = new THREE.BoxGeometry(1, 1, 1);
    const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
    const cube = new THREE.Mesh(geometry, material);
    cube.position.set(-0.3, 0.65, 0);
    // scene.add(cube);

    const planeGeometry = new THREE.PlaneGeometry(25, 25);
    const texture = new THREE.TextureLoader().load(
      "src/images/tri_pattern.jpg"
    );
    const plane = new THREE.Mesh(
      planeGeometry,
      new THREE.MeshPhongMaterial({ map: texture })
    );
    plane.rotateX(-Math.PI / 2);
    plane.receiveShadow = true;
    scene.add(plane);

    material1 = new THREE.MeshPhongMaterial({
      envMap: cubeRenderTarget.texture,
    });
    const ball1 = new THREE.Mesh(
      new THREE.SphereGeometry(1, 32, 32),
      material1
    );
    ball1.position.set(6, 1.1, 0);
    ball1.castShadow = true;
    ball1.receiveShadow = true;

    scene.add(ball1);
    // cubeCamera2.update(renderer, scene);
    cubeCamera.update(renderer, scene);

    pmremGenerator = new THREE.PMREMGenerator(renderer);
    pmremGenerator.compileEquirectangularShader();

    neutralEnvironment = pmremGenerator.fromScene(
      new RoomEnvironment()
    ).texture;

    controls = new OrbitControls(camera, renderer.domElement);
    controls.enabled = true;
    // controls.maxPolarAngle = 1.0;
    // controls.minPolarAngle = -0.5;
    // controls.enableDamping = true;
    // controls.screenSpacePanning = true;

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
      "src/models/van/van2.glb",
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

            // child.material.envMap = cubeRenderTarget2.texture;
            // console.log("child: ", child);
            console.log("child is: ", child);
            vanElement.map((dt) => {
              console.log("dt is: ", dt);
              if (dt == child.parent.name) {
                console.log("===: ", dt, child.parent.name);
                child.material.envMap = exrEnv;
              } else {
                child.material.envMap = cubeRenderTarget2.texture;
              }
            });
          }
        });
        cubeCamera2.update(renderer, scene);

        // cubeCamera.position.copy(cube);
      },
      undefined,
      function (error) {
        console.error(error);
      }
    );
    updateEnvironment();
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
    // cubeCamera.update(renderer, scene);
    // cubeCamera2.update(renderer, scene);
    // cubeCamera.update(renderer, scene);

    const delta = clock.getDelta();

    // childVan && childVan.rotateY(-0.3 * delta);
    // pivot2 && pivot2.rotateY(0.3 * delta);

    renderer.render(scene, camera);
  };
  function onWindowResize() {
    const width = window.innerWidth;
    const height = window.innerHeight;

    camera.updateProjectionMatrix();

    renderer.setSize(width, height);
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
