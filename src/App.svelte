<script>
  import * as THREE from "../build/three.module";
  import { onMount, tick } from "svelte";
  import { GLTFLoader } from "../js/GLTFLoader";
  import { OrbitControls } from "../js/OrbitControls";
  import { TWEEN } from "../js/tween.module.min.js";
  import { FlyControls } from "../js/FlyControls.js";

  let canvas, renderer;
  let controls;
  let controls2;
  let loader;
  let scene;
  let camera;
  let clock;
  let fittingRoom;
  let points = [];
  let xCenterBox, yCenterBox, zCenterBox;
  let distanceXOfbox, distanceYOfbox, distanceZOfbox;
  let boxHelper;
  let raycaster = new THREE.Raycaster();
  let mouse = new THREE.Vector2();
  let helper;
  let iron;
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
  startTime = new Date();
  let labelRenderer;
  // get seconds
  let seconds = Math.round(startTime);

  const widthScreen = window.innerWidth;
  const heightScreen = window.innerHeight;

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
    camera.position.set(12, 1, 5);
    camera.lookAt(0, 0, 0);
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

    const light1 = new THREE.AmbientLight(0xffffff, 0.3);
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
    controls.enabled = false;
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
      "src/models/fittting-room.gltf",
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

        console.log("fittingRoom: ", fittingRoom);
        scene.add(fittingRoom);

        gltf.scene.traverse(function (child) {
          if (child.isMesh) {
            console.log("in child.name: ", child.name);
          }
        });
      },
      undefined,
      function (error) {
        console.error(error);
      }
    );

    container.addEventListener("pointerdown", onPointerDown);

    container.addEventListener("pointermove", onPointerMoveMouse, false);
  };

  function getBoxObject(boxHelper) {
    for (var i = 0; i < 8; ++i) {
      var x = boxHelper.geometry.attributes.position.getX(i);
      var y = boxHelper.geometry.attributes.position.getY(i);
      var z = boxHelper.geometry.attributes.position.getZ(i);
      points.push({ x: x, y: y, z: z });
    }
    console.log("in points: ", points);
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

    console.log("centerBox: ", xCenterBox, yCenterBox, zCenterBox);
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
      if (intersects[0].face.normal === null) {
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
          clickedName === "ground"
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
          controls.enabled = false;
          isUserInteracting = true;
          controlCamera = true;
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

    controls.target.copy(camera.position).add(forward);
  }

  const animate = () => {
    requestAnimationFrame(animate);
    // cube.rotation.x += 0.01;
    // cube.rotation.y += 0.01;
    camera.position.y = 0.5;
    update();
    TWEEN.update();
    // composer.render();
    controls.addEventListener("end", () => {
      updateCameraOrbit();
    });
    controls2.update(clock.getDelta());
    renderer.render(scene, camera);
  };
  function onWindowResize() {
    // widthTest
    // heightTest    camera.aspect = widthScreen / heightScreen;

    camera.updateProjectionMatrix();

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

      // camera.lookAt( x, y, z );
      // if (camera.position.y < 0){
      camera.lookAt(x, y, z);

      // }

      // camera.lookAt(0,0,0);

      renderer.render(scene, camera);
    }
  }
  const getNameObject = () => {
    let intersects = raycaster.intersectObjects(scene.children, true);
    let clickedName = intersects[0].object.name;
    console.log("clickedName22: ", clickedName);
  };
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
    on:mouseup={moveCamera}
    on:mousedown={startTimer}
    on:click={getNameObject}
  />
</main>

<style>
  .full-screen {
    margin: 0 !important;
    padding: 0 !important;
  }
</style>
