<script>
  import * as THREE from "../build/three.module";
  import { onMount, tick } from "svelte";
  import { GLTFLoader } from "../js/GLTFLoader";
  import { OrbitControls } from "../js/OrbitControls";
  import { TWEEN } from "../js/tween.module.min.js";
  import { FlyControls } from "../js/FlyControls.js";
  import SimpleModal from "./components/modal/index.svelte";
  import { OutlinePass } from "../js/bloomEffect/OutlinePass.js";
  import { OutputPass } from "../js/bloomEffect/OutputPass.js";

  // import { OBJLoader } from './js/OBJLoader.js';
  import { EffectComposer } from "../js/EffectComposer.js";
  import { RenderPass } from "../js/RenderPass.js";
  import { ShaderPass } from "../js/bloomEffect/ShaderPass.js";
  import { CopyShader } from "../js/bloomEffect/CopyShader.js";
  import { FXAAShader } from "../js/bloomEffect/FXAAShader.js";
  import { GUI } from "../js/lil-gui.module.min.js";
  import { CSS2DRenderer, CSS2DObject } from "../js/CSS2DRenderer.js";
  import { CSS3DRenderer, CSS3DObject } from "../js/CSS3DRenderer.js";

  import { Split } from "@geoffcox/svelte-splitter";

  let canvas, renderer;
  let controls;
  let controls2;
  let loader;
  let scene;
  let camera;
  let clock;
  let fittingRoom;
  let shirt;
  let points = [];
  let hoveredObjects = [];
  let xCenterBox, yCenterBox, zCenterBox;
  let distanceXOfbox, distanceYOfbox, distanceZOfbox;
  let boxHelper;
  let raycaster = new THREE.Raycaster();
  let mouse = new THREE.Vector2();
  let helper;
  let iron;
  8;
  let boxHover;
  let shirtHover = null;
  let simpleModalRef;
  let showModal = false;
  let groupShirt;
  let moveCameraClick = true;
  let isUserInteracting = false,
    onPointerDownMouseX = 0,
    onPointerDownMouseY = 0,
    lon = 0,
    onPointerDownLon = 0,
    lat = 0,
    onPointerDownLat = 0,
    phi = 0,
    theta = 0;
  let controlCamera = false;
  let startTime, endTime;
  let composer, effectFXAA, outlinePass;
  startTime = new Date();
  let labelRenderer;
  let selectedObjects = [];
  let cssRenderer;
  let textButtonView = "Go to Mall";
  const params = {
    edgeStrength: 3.0,
    edgeGlow: 0.0,
    edgeThickness: 1.0,
    pulsePeriod: 0,
    rotate: false,
    usePatternTexture: false,
  };
  let isGoMallMode = false;
  $: console.log("selectedObjects: ", selectedObjects);

  // get seconds
  let seconds = Math.round(startTime);

  const widthScreen = window.innerWidth;
  const heightScreen = window.innerHeight;
  $: console.log("canvas: ", canvas);
  $: console.log("shirtHover: ", shirtHover);
  $: console.log("showModal: ", showModal);
  $: console.log("controls: 0", controls);
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
      70,
      widthScreen / heightScreen,
      0.1,
      1000
    );
    scene = new THREE.Scene();
    // camera.position.set(12, 5, 5);
    camera.position.set(0, 10, 10);

    camera.lookAt(1, 0, 0);
    //create ground
    const planeMesh = new THREE.Mesh(
      new THREE.PlaneGeometry(400, 200),
      new THREE.MeshBasicMaterial({
        color: 0x6f7a73,
        side: THREE.DoubleSide,
        visible: false,
      })
    );

    planeMesh.rotateX(Math.PI / 2);
    planeMesh.name = "ground";
    planeMesh.position.set(0, 0.2, 0);

    scene.add(planeMesh);

    const visiablePlane = new THREE.Mesh(
      new THREE.PlaneGeometry(400, 200),
      new THREE.MeshBasicMaterial({
        color: 0x6f7a73,
        side: THREE.DoubleSide,
        visible: true,
      })
    );

    visiablePlane.rotateX(Math.PI / 2);
    visiablePlane.name = "ground";
    visiablePlane.position.set(0, 0, 0);

    scene.add(visiablePlane);

    clock = new THREE.Clock();
    const Camhelper = new THREE.CameraHelper(camera);
    // scene.add(Camhelper);

    // scene.background = reflectionCube;
    scene.background = new THREE.Color(0xffffff);
    //Load background texture
    const mainBackground = new THREE.TextureLoader();
    mainBackground.load("src/assets/star-sky.jpg", function (texture) {
      scene.background = texture;
    });

    const light1 = new THREE.AmbientLight(0xffffff, 1);
    light1.name = "ambient_light";
    scene.add(light1);

    const light = new THREE.DirectionalLight(0xffffff, 0.8 * Math.PI);
    scene.add(light);

    const hemiLight = new THREE.HemisphereLight();

    scene.add(hemiLight);
    renderer = new THREE.WebGLRenderer({ canvas });
    // renderer.setSize(1306, 308);

    renderer.setSize(widthScreen, heightScreen);

    controls = new OrbitControls(camera, renderer.domElement);
    controls.enabled = false ? isGoMallMode : true;
    controls.maxPolarAngle = 1.0;
    controls.minPolarAngle = -0.5;

    controls2 = new FlyControls(camera, renderer.domElement);
    controls2.movementSpeed = 10;

    let container = document.getElementById("container");
    loader = new GLTFLoader();

    //Pointer
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
      "src/models/blue_jacket.gltf",
      function (gltf) {
        shirt = gltf.scene;
        // shirt.scale.set(0.5, 0.5, 0.5);
        // boxHelper = new THREE.BoxHelper(fittingRoom, 0xff0000);

        // scene.add(boxHelper);
        // getBoxObject(boxHelper);
        // boxHelper.position.y = -distanceYOfbox / 2;
        // boxHelper.position.x = -distanceXOfbox / 2;
        // fittingRoom.position.y = distanceYOfbox / 2;
        // fittingRoom.position.x = -distanceXOfbox / 2;
        // fittingRoom.position.z = distanceZOfbox / 2;

        shirt.position.set(1, 0.5, 1);
        shirt.scale.set(1, 1, 1);
        scene.add(shirt);

        // gltf.scene.traverse(function (child) {
        //   if (child.isMesh) {
        //     // console.log("in child.name: ", child.name);
        //     // const groupShirt = new THREE.Group();
        //     // groupShirt.add(child);
        //     // groupShirt.name = "shirt";
        //     // scene.add(groupShirt);
        //   }
        // });
      },
      undefined,
      function (error) {
        console.error(error);
      }
    );

    loader.load(
      "src/models/motorbike/scene.gltf",
      function (gltf) {
        fittingRoom = gltf.scene;
        fittingRoom.scale.set(0.5, 0.5, 0.5);
        boxHelper = new THREE.BoxHelper(fittingRoom, 0xff0000);
        // scene.add(boxHelper);
        getBoxObject(boxHelper);
        // boxHelper.position.y = -distanceYOfbox / 2;
        // boxHelper.position.x = -distanceXOfbox / 2;
        fittingRoom.position.y = distanceYOfbox / 2;
        fittingRoom.position.x = -distanceXOfbox / 2;
        fittingRoom.position.z = distanceZOfbox / 2;

        scene.add(fittingRoom);

        gltf.scene.traverse(function (child) {
          if (child.isMesh) {
          }
        });
      },
      undefined,
      function (error) {
        console.error(error);
      }
    );

    // postprocessing

    composer = new EffectComposer(renderer);

    const renderPass = new RenderPass(scene, camera);
    composer.addPass(renderPass);

    outlinePass = new OutlinePass(
      new THREE.Vector2(window.innerWidth, window.innerHeight),
      scene,
      camera
    );

    composer.addPass(outlinePass);

    const textureLoader = new THREE.TextureLoader();
    textureLoader.load("./images/tri_pattern.jpg", function (texture) {
      outlinePass.patternTexture = texture;
      texture.wrapS = THREE.RepeatWrapping;
      texture.wrapT = THREE.RepeatWrapping;
    });

    effectFXAA = new ShaderPass(FXAAShader);
    effectFXAA.uniforms["resolution"].value.set(
      1 / window.innerWidth,
      1 / window.innerHeight
    );
    composer.addPass(effectFXAA);

    function addSelectedObject(object) {
      selectedObjects = [];
      if (shirt) {
        selectedObjects.push(shirt);
      }

      outlinePass.selectedObjects = selectedObjects;
    }

    addSelectedObject();

    // function checkIntersection() {
    //   raycaster.setFromCamera(mouse, camera);

    //   const intersects = raycaster.intersectObject(scene, true);

    //   if (intersects.length > 0) {
    //     const selectedObject = intersects[0].object;
    //     addSelectedObject(selectedObject);
    //     outlinePass.selectedObjects = selectedObjects;
    //     console.log("selectedObjects: ", selectedObjects);
    //   } else {
    //     // outlinePass.selectedObjects = [];
    //   }
    // }

    const gui = new GUI({ width: 280 });

    gui.add(params, "edgeStrength", 0.01, 10).onChange(function (value) {
      outlinePass.edgeStrength = Number(value);
    });

    gui.add(params, "edgeGlow", 0.0, 1).onChange(function (value) {
      outlinePass.edgeGlow = Number(value);
    });

    gui.add(params, "edgeThickness", 1, 4).onChange(function (value) {
      outlinePass.edgeThickness = Number(value);
    });

    gui.add(params, "pulsePeriod", 0.0, 5).onChange(function (value) {
      outlinePass.pulsePeriod = Number(value);
    });

    gui.add(params, "rotate");

    gui.add(params, "usePatternTexture").onChange(function (value) {
      outlinePass.usePatternTexture = value;
    });

    function Configuration() {
      this.visibleEdgeColor = "#ffffff";
      this.hiddenEdgeColor = "#190a05";
    }

    const conf = new Configuration();

    gui.addColor(conf, "visibleEdgeColor").onChange(function (value) {
      outlinePass.visibleEdgeColor.set(value);
    });

    gui.addColor(conf, "hiddenEdgeColor").onChange(function (value) {
      outlinePass.hiddenEdgeColor.set(value);
    });

    const hoverObject = (event) => {
      mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
      mouse.y = -(event.clientY / window.innerHeight) * 2 + 1;
      raycaster.setFromCamera(mouse, camera);
      let intersects = raycaster.intersectObject(scene, true);

      if (intersects.length > 0) {
        const selectedObject = intersects[0].object;

        hoveredObjects.map((obj, key) => {
          if (obj.name == selectedObject.name) {
            console.log("keyss: ", key);
            console.log("hover nao nao");
            addSelectedObject(hoveredObjects[key]);
          }
        });
      }
    };

    const clickShowObject = () => {
      let intersects = raycaster.intersectObjects(scene.children, true);
      let clickedName = intersects[0].object;
      console.log("clickedName22: ", clickedName);
      if (clickedName.name == "Mesh_0") {
        // boxHover = new THREE.BoxHelper(intersects[0].object, 0xff0000);

        // scene.add(boxHover);
        showModal = true;
      }
    };

    // Create CSS2DRenderer
    cssRenderer = new CSS2DRenderer();
    cssRenderer.setSize(window.innerWidth, window.innerHeight);
    document.body.appendChild(cssRenderer.domElement);

    // Create a button as a CSS2DObject
    const button = createButton("Click me!", () => {
      console.log("Button clicked!");
    });
    button.position.set(0, 0, 0); // Adjust the position in 3D space
    scene.add(button);

    // function onPointerMove(event) {
    //   if (event.isPrimary === false) return;

    //   mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
    //   mouse.y = -(event.clientY / window.innerHeight) * 2 + 1;

    //   // checkIntersection();
    // }
    container.addEventListener("pointerdown", onPointerDown);
    container.addEventListener("click", clickShowObject);

    // container.addEventListener("pointermove", hoverObject, false);
    // container.addEventListener("pointermove", onPointerMove, false);

    container.addEventListener("pointermove", onPointerMoveMouse, false);
  };

  const createButton = (text, onClick) => {
    const buttonElement = document.createElement("button");
    buttonElement.textContent = text;
    buttonElement.addEventListener("click", onClick);

    const buttonObject = new CSS2DObject(buttonElement);
    console.log("buttonObject: ", buttonObject);
    return buttonObject;
  };
  function getBoxObject(boxHelper) {
    for (var i = 0; i < 8; ++i) {
      var x = boxHelper.geometry.attributes.position.getX(i);
      var y = boxHelper.geometry.attributes.position.getY(i);
      var z = boxHelper.geometry.attributes.position.getZ(i);
      points.push({ x: x, y: y, z: z });
    }
    distanceXOfbox = new THREE.Vector3(
      points[0].x,
      points[0].y,
      points[0].z
    ).distanceTo(new THREE.Vector3(points[1].x, points[1].y, points[1].z));
    distanceYOfbox = new THREE.Vector3(
      points[1].x,
      points[1].y,
      points[1].z
    ).distanceTo(new THREE.Vector3(points[2].x, points[2].y, points[2].z));
    distanceZOfbox = new THREE.Vector3(
      points[1].x,
      points[1].y,
      points[1].z
    ).distanceTo(new THREE.Vector3(points[5].x, points[5].y, points[5].z));

    console.log("vi tri y getbox la: ", points[1].x, points[1].y, points[1].z);
    console.log(
      "vi tri y getbox 2 la: ",
      points[2].x,
      points[2].y,
      points[2].z
    );
    //get center Point of BoxHelper

    xCenterBox = (points[0].x + points[1].x) / 2;
    yCenterBox = (points[1].y + points[2].y) / 2;
    // z_centerBox = (points[3].z+ points[4].z)/2
    zCenterBox = (points[2].z + points[6].z) / 2;
  }
  function onPointerDown(event) {
    if (event.isPrimary === false) return;

    moveCameraClick = false;

    onPointerDownMouseX = event.clientX;
    onPointerDownMouseY = event.clientY;

    onPointerDownLon = lon;
    onPointerDownLat = lat;
    document.addEventListener("pointermove", onPointerMove);
    document.addEventListener("pointerup", onPointerUp);
    scene.remove(helper);
  }

  function onPointerMove(event) {
    if (event.isPrimary === false) return;
    lon = (onPointerDownMouseX - event.clientX) * 0.1 + onPointerDownLon;
    lat = (event.clientY - onPointerDownMouseY) * 0.1 + onPointerDownLat;
  }

  //icon chuột hover
  function onPointerMoveMouse(event) {
    mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
    mouse.y = -(event.clientY / window.innerHeight) * 2 + 1;

    raycaster.setFromCamera(mouse, camera);

    let intersects = raycaster.intersectObjects(scene.children, true);

    if (intersects.length > 0) {
      helper.position.set(0, 0, 0);
      // console.log('in intersects[0]: ',intersects[ 0 ])
      // helper.lookAt( intersects[ 0 ].face.area );
      if (intersects[0].face && intersects[0].face.normal === null) {
      } else {
        helper.lookAt(intersects[0].face.normal);
      }

      // helper.lookAt( intersects[ 0 ].object.isObject3D );

      helper.position.copy(intersects[0].point);
      scene.add(helper);
    }
  }

  function onPointerUp() {
    if (event.isPrimary === false) return;
    // isUserInteracting = false;

    document.removeEventListener("pointermove", onPointerMove);

    document.removeEventListener("pointerup", onPointerUp);
  }

  //Di chuyển trên sàn
  function startTimer() {
    //rotation_speed = 0;
    startTime = new Date();
    moveCameraClick = true;
    scene.remove(helper);
    event.preventDefault();
    mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
    mouse.y = -(event.clientY / window.innerHeight) * 2 + 1;
    raycaster.setFromCamera(mouse, camera);

    //let intersects = raycaster.intersectObjects( scene.children, true );
  }
  function moveCamera(event) {
    endTime = new Date();
    let timeDiff = endTime - startTime; //in ms
    // strip the ms
    timeDiff /= 500;

    // get seconds
    seconds = Math.round(timeDiff);
    console.log(seconds + " seconds");

    event.preventDefault();
    mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
    mouse.y = -(event.clientY / window.innerHeight) * 2 + 1;
    raycaster.setFromCamera(mouse, camera);

    let intersects = raycaster.intersectObjects(scene.children, true);
    if (moveCameraClick == true) {
      if (intersects.length > 0) {
        let clickedName = intersects[0].object.name;
        let selectedObject = intersects[0].object;
        console.log("in clickedName: ", clickedName);
        console.log("in seconds: ", seconds);
        console.log(
          "in intersects[0].object.isObject3D: ",
          intersects[0].object.isObject3D
        );
        if (
          intersects[0].object.isObject3D &&
          seconds < 0.05 &&
          clickedName === "ground" &&
          isGoMallMode == true
        ) {
          console.log("Dang vao duoc dieu huong");
          let coords = {
            x: camera.position.x,
            y: camera.position.y,
            z: camera.position.z,
          };
          console.log("x pos: ", intersects[0].point.x);
          new TWEEN.Tween(coords)
            .to({
              x: intersects[0].point.x,
              y: 0.5,
              z: intersects[0].point.z,
            })
            .onUpdate(() => camera.position.set(coords.x, coords.y, coords.z))
            .start();
          // controls.enabled = false;
          // isUserInteracting = true;
          // controlCamera = true;
        } else {
          console.log("Ko Dang vao duoc dieu huong");
        }
      }
    }
  }

  function updateCameraOrbit() {
    // Update OrbitControls target to a point just in front of the camera

    var forward = new THREE.Vector3();
    camera.getWorldDirection(forward);

    // controls.target.copy(camera.position).add(forward);
  }

  const animate = () => {
    requestAnimationFrame(animate);
    // cube.rotation.x += 0.01;
    // cube.rotation.y += 0.01;
    // camera.position.y = 0.5;
    update();
    TWEEN.update();
    composer.render();
    // controls.addEventListener("end", () => {
    //   updateCameraOrbit();
    // });

    cssRenderer.render(scene, camera);

    controls2.update(clock.getDelta());
    renderer.render(scene, camera);
  };
  function onWindowResize() {
    const width = window.innerWidth;
    const height = window.innerHeight;
    // widthTest
    // heightTest    camera.aspect = widthScreen / heightScreen;

    camera.updateProjectionMatrix();
    composer.setSize(width, height);

    effectFXAA.uniforms["resolution"].value.set(
      1 / window.innerWidth,
      1 / window.innerHeight
    );
    renderer.setSize(widthScreen, heightScreen);
  }

  function update() {
    if (isUserInteracting === false) {
      lon += 0.03;
    }

    if (controlCamera === true) {
      // console.log(' da vao controlCamera: ',controlCamera)

      lat = Math.max(-120, Math.min(120, lat));
      phi = THREE.MathUtils.degToRad(90 - lat);
      theta = THREE.MathUtils.degToRad(lon);

      let x = 500 * Math.sin(phi) * Math.cos(theta);
      let y = 500 * Math.cos(phi);
      let z = 500 * Math.sin(phi) * Math.sin(theta);

      camera.lookAt(x, y, z);

      renderer.render(scene, camera);
    }
  }
  const getNameObject = () => {
    // showModal = true;
    let intersects = raycaster.intersectObjects(scene.children, true);
    // let clickedName = intersects[0].object;
    // console.log("clickedName22: ", clickedName);
    // if (clickedName == "mesh_0") {
    //   boxHover = new THREE.BoxHelper(intersects[0].object, 0xff0000);
    //   console.log("in BoxHover 1: ", boxHover.object.name);
    //   // boxHover.update();
    //   scene.add(boxHover);
    // }
  };

  const showInfoModel = () => {};

  const closeInfomodel = () => {};

  function onOverViewButton() {
    isGoMallMode = !isGoMallMode;
    if (isGoMallMode) {
      isUserInteracting = true;
      controlCamera = true;
      controls.enabled = false;
      let coords = {
        x: 0,
        y: 10,
        z: 10,
      };
      new TWEEN.Tween(coords)
        .to(
          {
            x: 0, // Lùi ra phía sau tòa nhà
            y: 1,
            z: 5,
          },
          1000
        )
        .onUpdate(() => {
          camera.position.set(coords.x, coords.y, coords.z); // Từ vị trí đâu xuống
          // camera.lookAt(1, 0, 0);
          return camera;
        })
        .start();
    } else {
      isUserInteracting = false;
      controlCamera = false;
      controls.enabled = true;
      let coords = {
        x: 0,
        y: 1,
        z: 5,
      };
      new TWEEN.Tween(coords)
        .to(
          {
            x: 0, // Lùi ra phía sau tòa nhà
            y: 10,
            z: 10,
          },
          1000
        )
        .onUpdate(() => {
          camera.position.set(coords.x, coords.y, coords.z); // Từ vị trí đâu xuống
          camera.lookAt(1, 0, 0);
          return camera;
        })
        .start();
    }
  }

  const handleZoom = (e) => {
    console.log("eeee zz: ", e);
  };

  onMount(() => {
    init();
    animate();

    window.addEventListener("resize", onWindowResize);
  });
</script>

<div class="view-button">
  <button
    style="--focus-color: {isGoMallMode
      ? '#1d6291'
      : '#1f9bed'}; --focus-border: {isGoMallMode ? '2px solid blue' : 'none'}"
    on:click={onOverViewButton}>{textButtonView}</button
  >
</div>
<main>
  <canvas
    class="full-screen"
    id="container"
    bind:this={canvas}
    on:click={moveCamera}
    on:mousedown={startTimer}
    on:click={getNameObject}
    on:zoom={handleZoom}
  >
  </canvas>
</main>

<SimpleModal
  bind:this={simpleModalRef}
  heightSize={"250px"}
  on:clickButton={showInfoModel}
  on:closeButton={closeInfomodel}
  saveButtonName={"Save AA"}
  bind:showModal
>
  <div slot="content">
    <div>
      Áo Thun Trơn Áo Phông Trắng Đen Xám Nam Nữ Form Xuông Vải Dày Mịn Không Xù
      Lông
    </div>
    <div class="detail-product">
      <Split initialPrimarySize="70%">
        <div slot="primary" class="left-content">
          <div>Price</div>
          <div>About Product</div>
          <div>Orgin</div>
          <div>Color</div>
          <div>Size</div>
        </div>
        <div slot="secondary" class="right-content">haha</div>
      </Split>
    </div>
  </div>
</SimpleModal>

<style>
  .full-screen {
    margin: 0 !important;
    padding: 0 !important;
  }

  .view-button {
    left: 50%;
    position: fixed;
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
