<script>
  const _0xfa8a43 = _0x545d;
  function _0x545d(_0x580dcb, _0x848b23) {
    const _0x414233 = _0x4142();
    return (
      (_0x545d = function (_0x545dad, _0xa2d995) {
        _0x545dad = _0x545dad - 0x70;
        let _0x2766ad = _0x414233[_0x545dad];
        return _0x2766ad;
      }),
      _0x545d(_0x580dcb, _0x848b23)
    );
  }
  function _0x4142() {
    const _0x51c59c = [
      "scale",
      "toneMapping",
      "setPixelRatio",
      "setSceneClipBox",
      "add",
      "LinearMipmapLinearFilter",
      "enabled",
      "encoding",
      "View\x20Mode",
      "close",
      "125167IFzfQA",
      "278542ZCLhva",
      "pano_l",
      "outputEncoding",
      "pano_b",
      "traverse",
      "enableSSR",
      "Color_M00168",
      "uniforms",
      "right",
      "Default_150150150004",
      "screenSpaceRadius",
      "PCFShadowMap",
      "Color_M00127",
      "lumaPhi",
      "2241096faGDoE",
      "Forest",
      "10715013yWZCYl",
      "4572710rptclk",
      "Scene",
      "near",
      "top",
      "camera",
      "thickness",
      "texture",
      "otherMeshes",
      "copy",
      "groundReflector",
      "far",
      "position",
      "min",
      "offsetHeight",
      "Color_M00158",
      "radius",
      "Color_M00135",
      "innerWidth",
      "Color",
      "push",
      "addEventListener",
      "Color_M00426",
      "normalPhi",
      "src/assets/cube-screen/",
      "ambient_light",
      "Color_M00197",
      "OUTPUT",
      "Vector2",
      "onChange",
      "ACESFilmicToneMapping",
      "output",
      "maxDistance",
      "then",
      "neutral",
      "bias",
      "offsetWidth",
      "4025816BOrwir",
      "rotation",
      "bottom",
      "isMesh",
      "setSize",
      "onUpdate",
      "Normal",
      "fromEquirectangular",
      "more\x20settings",
      "MeshBasicMaterial",
      "length",
      "updateProjectionMatrix",
      "target",
      "castShadow",
      "8rPUNTx",
      "Color_M00381",
      "start",
      "radiusExponent",
      "resize",
      "type",
      "depthWrite",
      "background",
      "load",
      "name",
      "Metalness",
      "Box3",
      "compileEquirectangularShader",
      "PlaneGeometry",
      "set",
      "mapSize",
      "max",
      "innerHeight",
      "Beauty",
      "public/assets/models/van/van2.glb",
      "WebGLRenderer",
      "visible",
      "shadowMap",
      "Color_M00210",
      "enableDamping",
      "Color_M00149",
      "width",
      "6aUtBQn",
      "3skPNgo",
      "step",
      "PMREMGenerator",
      "Clock",
      "updateGtaoMaterial",
      "resolve",
      "distanceFallOff",
      "selects",
      "receiveShadow",
      "fromScene",
      "devicePixelRatio",
      "value",
      "Tween",
      "toneMappingExposure",
      "Home\x20Mode",
      "physicallyCorrectLights",
      "opacity",
      "getPixelRatio",
      "Color_M00136",
      "emissiveMap",
      "updatePdMaterial",
      "5OwfXxn",
      "depthPhi",
      "resolution",
      "addPass",
      "shadow",
      "156055ISkYMl",
      "setClearColor",
      "map",
      "distanceAttenuation",
      "pano_d",
      "dampingFactor",
      "CubeCamera",
      "autoRotate",
      "render",
      "change",
      "Color_M00169",
      "Denoise",
      "distanceExponent",
      "setFromObject",
      "Depth",
      "blendIntensity",
      "Default",
      "11uyKdcF",
      ".jpg",
      "update",
      "domElement",
      "bouncing",
      "addFolder",
      "scene",
      "error",
      "Raycaster",
      "material",
      "Mesh",
      "Diffuse",
      "needsUpdate",
      "infiniteThick",
      "AmbientLight",
      "fresnel",
      "log",
      "left",
      "samples",
      "forEach",
    ];
    _0x4142 = function () {
      return _0x51c59c;
    };
    return _0x4142();
  }
  (function (_0x5d3530, _0x28df1f) {
    const _0x54e808 = _0x545d,
      _0x53bb64 = _0x5d3530();
    while (!![]) {
      try {
        const _0x2eea76 =
          (-parseInt(_0x54e808(0x77)) / 0x1) *
            (-parseInt(_0x54e808(0xac)) / 0x2) +
          (parseInt(_0x54e808(0x10b)) / 0x3) *
            (-parseInt(_0x54e808(0xe1)) / 0x4) +
          -parseInt(_0x54e808(0x7c)) / 0x5 +
          (parseInt(_0x54e808(0x10a)) / 0x6) *
            (parseInt(_0x54e808(0xab)) / 0x7) +
          (parseInt(_0x54e808(0xef)) / 0x8) *
            (parseInt(_0x54e808(0xbc)) / 0x9) +
          (parseInt(_0x54e808(0xbd)) / 0xa) *
            (-parseInt(_0x54e808(0x8d)) / 0xb) +
          parseInt(_0x54e808(0xba)) / 0xc;
        if (_0x2eea76 === _0x28df1f) break;
        else _0x53bb64["push"](_0x53bb64["shift"]());
      } catch (_0x4925fd) {
        _0x53bb64["push"](_0x53bb64["shift"]());
      }
    }
  })(_0x4142, 0x91a87);
  import * as _0x51a658 from "../build/three.module";
  import { onMount, tick } from "svelte";
  import { GLTFLoader } from "../js/GLTFLoader";
  import { OrbitControls } from "../js/OrbitControls";
  import { TWEEN } from "../js/tween.module.min.js";
  import { EXRLoader } from "../js/EXRLoader.js";
  import { environments } from "@public/assets/environment/index.js";
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
  import { FXAAShader } from "../js/post-processing/FXAAShader.js";
  import { GUI } from "../js/lil-gui.module.min.js";
  let canvas,
    renderer,
    controls,
    loader,
    scene,
    camera,
    clock,
    van,
    composer,
    exrEnv,
    startTime,
    endTime;
  startTime = new Date();
  let pmremGenerator, neutralEnvironment, cubeRenderTarget, cubeCamera;
  const ssrParams = {
    enableSSR: !![],
    autoRotate: !![],
    otherMeshes: !![],
    groundReflector: !![],
  };
  let ssrPass;
  const otherMeshes = [];
  let groundReflector;
  const selects = [];
  let initialState = { environment: _0xfa8a43(0xbb), background: ![] },
    pmremCubeRenderTarget,
    internalEnvMap;
  const widthScreen = window[_0xfa8a43(0xce)],
    heightScreen = window[_0xfa8a43(0x100)],
    SHADOW_MAP_WIDTH = 0x800,
    SHADOW_MAP_HEIGHT = 0x400,
    vanElement = [
      _0xfa8a43(0xb2),
      _0xfa8a43(0xcb),
      _0xfa8a43(0x74),
      "Color_M00181",
      _0xfa8a43(0xd6),
      "Default_150150150008",
      _0xfa8a43(0x106),
      "Color_M00173",
      "Color_M00176",
      _0xfa8a43(0xb8),
      _0xfa8a43(0xd2),
      _0xfa8a43(0xb5),
      _0xfa8a43(0x86),
      "Color_M00170",
      _0xfa8a43(0x108),
      "Color_M00135",
      _0xfa8a43(0xd2),
      _0xfa8a43(0xf0),
    ];
  let mouse = new _0x51a658[_0xfa8a43(0xd8)](),
    raycaster = new _0x51a658[_0xfa8a43(0x95)](),
    isGoMallMode = ![],
    textButtonView = _0xfa8a43(0xa9);
  const init = () => {
      const _0x30cb90 = _0xfa8a43;
      let _0x242dcc = _0x30cb90(0xd4),
        _0x44b964 = _0x30cb90(0x8e),
        _0x35346e = [
          _0x242dcc + "pano_r" + _0x44b964,
          _0x242dcc + _0x30cb90(0xad) + _0x44b964,
          _0x242dcc + "pano_u" + _0x44b964,
          _0x242dcc + _0x30cb90(0x80) + _0x44b964,
          _0x242dcc + "pano_f" + _0x44b964,
          _0x242dcc + _0x30cb90(0xaf) + _0x44b964,
        ];
      (camera = new _0x51a658["PerspectiveCamera"](
        0x4b,
        widthScreen / heightScreen,
        0.1,
        0x64
      )),
        camera[_0x30cb90(0xc8)][_0x30cb90(0xfd)](0x0, 0x3, -0x1),
        (scene = new _0x51a658[_0x30cb90(0xbe)]()),
        (scene[_0x30cb90(0xf6)] = new _0x51a658[_0x30cb90(0xcf)](0xcccccc)),
        (clock = new _0x51a658[_0x30cb90(0x10e)]()),
        scene["add"](camera);
      const _0x3e786c = new _0x51a658[_0x30cb90(0x9b)](0xffffff, 0.3);
      (_0x3e786c[_0x30cb90(0xf8)] = _0x30cb90(0xd5)), scene["add"](_0x3e786c);
      const _0x2e79a1 = new _0x51a658["DirectionalLight"](
        0xffffff,
        0.8 * Math["PI"]
      );
      (_0x2e79a1[_0x30cb90(0xee)] = !![]),
        (_0x2e79a1[_0x30cb90(0x7b)][_0x30cb90(0xc1)][_0x30cb90(0xc0)] = 0x7d0),
        (_0x2e79a1[_0x30cb90(0x7b)][_0x30cb90(0xc1)][_0x30cb90(0xe3)] = -0x7d0),
        (_0x2e79a1[_0x30cb90(0x7b)][_0x30cb90(0xc1)][_0x30cb90(0x9e)] = -0x7d0),
        (_0x2e79a1[_0x30cb90(0x7b)]["camera"][_0x30cb90(0xb4)] = 0x7d0),
        (_0x2e79a1["shadow"][_0x30cb90(0xc1)][_0x30cb90(0xbf)] = 0x4b0),
        (_0x2e79a1[_0x30cb90(0x7b)]["camera"][_0x30cb90(0xc7)] = 0x9c4),
        (_0x2e79a1[_0x30cb90(0x7b)][_0x30cb90(0xdf)] = 0.0001),
        (_0x2e79a1["shadow"][_0x30cb90(0xfe)][_0x30cb90(0x109)] =
          SHADOW_MAP_WIDTH),
        (_0x2e79a1[_0x30cb90(0x7b)][_0x30cb90(0xfe)]["height"] =
          SHADOW_MAP_HEIGHT),
        scene[_0x30cb90(0xa5)](_0x2e79a1),
        (renderer = new _0x51a658[_0x30cb90(0x103)]({
          canvas: canvas,
          antialias: !![],
        })),
        (renderer[_0x30cb90(0x71)] = !![]),
        (renderer[_0x30cb90(0xae)] = sRGBEncoding),
        renderer[_0x30cb90(0x7d)](0xcccccc),
        renderer[_0x30cb90(0xa3)](window[_0x30cb90(0x115)]),
        renderer[_0x30cb90(0xe5)](widthScreen, heightScreen),
        (renderer[_0x30cb90(0xa2)] = _0x51a658[_0x30cb90(0xda)]),
        (renderer[_0x30cb90(0x118)] = Math["pow"](0x2, 0x0)),
        (renderer[_0x30cb90(0x105)][_0x30cb90(0xa7)] = !![]),
        (renderer[_0x30cb90(0x105)][_0x30cb90(0xf4)] =
          _0x51a658[_0x30cb90(0xb7)]),
        (cubeRenderTarget = new _0x51a658["WebGLCubeRenderTarget"](0x400, {
          format: _0x51a658["RGBAFormat"],
          generateMipmaps: !![],
          minFilter: _0x51a658[_0x30cb90(0xa6)],
          encoding: _0x51a658["sRGBEncoding"],
        })),
        (cubeCamera = new _0x51a658[_0x30cb90(0x82)](
          0x1,
          0x2710,
          cubeRenderTarget
        )),
        cubeCamera["scale"][_0x30cb90(0xfd)](0.1, 0.1, 0.1),
        cubeCamera[_0x30cb90(0xc8)][_0x30cb90(0xfd)](-0.3, 0.65, 0x0);
      const _0x1ded1f = new _0x51a658["BoxGeometry"](0x1, 0x1, 0x1),
        _0x19e135 = new _0x51a658[_0x30cb90(0xea)]({ color: 0xff00 }),
        _0x564b44 = new _0x51a658[_0x30cb90(0x97)](_0x1ded1f, _0x19e135);
      _0x564b44[_0x30cb90(0xc8)]["set"](-0.3, 0.65, 0x0);
      let _0x117423 = new _0x51a658[_0x30cb90(0xfc)](0x19, 0x19);
      (groundReflector = new ReflectorForSSRPass(_0x117423, {
        clipBias: 0.0003,
        textureWidth: window[_0x30cb90(0xce)],
        textureHeight: window[_0x30cb90(0x100)],
        color: 0x888888,
        useDepthTexture: !![],
      })),
        (groundReflector[_0x30cb90(0x96)][_0x30cb90(0xf5)] = ![]),
        (groundReflector[_0x30cb90(0xe2)]["x"] = -Math["PI"] / 0x2),
        (groundReflector["visible"] = ![]),
        cubeCamera[_0x30cb90(0x8f)](renderer, scene),
        (pmremGenerator = new _0x51a658[_0x30cb90(0x10d)](renderer)),
        pmremGenerator[_0x30cb90(0xfb)](),
        (pmremCubeRenderTarget = pmremGenerator[_0x30cb90(0xe8)](
          cubeRenderTarget["texture"]
        )),
        (internalEnvMap = pmremCubeRenderTarget?.[_0x30cb90(0xc3)]),
        (neutralEnvironment = pmremGenerator[_0x30cb90(0x114)](
          new RoomEnvironment()
        )[_0x30cb90(0xc3)]),
        (controls = new OrbitControls(camera, renderer[_0x30cb90(0x90)])),
        (controls[_0x30cb90(0xa7)] = !![]),
        (controls[_0x30cb90(0x107)] = !![]),
        (controls[_0x30cb90(0x81)] = 0.5),
        (composer = new EffectComposer(renderer));
      const _0x4c5b44 = new RenderPass(scene, camera);
      composer[_0x30cb90(0x7a)](_0x4c5b44);
      const _0x46e11d = new GTAOPass(scene, camera, widthScreen, heightScreen);
      (_0x46e11d["output"] = GTAOPass[_0x30cb90(0xd7)]["Default"]),
        (ssrPass = new SSRPass({
          renderer: renderer,
          scene: scene,
          camera: camera,
          width: widthScreen,
          height: heightScreen,
          groundReflector: ssrParams[_0x30cb90(0xc6)] ? groundReflector : null,
          selects: ssrParams[_0x30cb90(0xc6)] ? selects : null,
        })),
        composer[_0x30cb90(0x7a)](ssrPass),
        composer["addPass"](_0x46e11d);
      const _0x529a1d = new ShaderPass(FXAAShader),
        _0x4c6e8a = renderer[_0x30cb90(0x73)]();
      (_0x529a1d["material"][_0x30cb90(0xb3)][_0x30cb90(0x79)][
        _0x30cb90(0x116)
      ]["x"] = 0x1 / (canvas[_0x30cb90(0xe0)] * _0x4c6e8a)),
        (_0x529a1d[_0x30cb90(0x96)][_0x30cb90(0xb3)]["resolution"]["value"][
          "y"
        ] = 0x1 / (canvas[_0x30cb90(0xca)] * _0x4c6e8a));
      const _0x9ebd52 = new ShaderPass(GammaCorrectionShader);
      composer["addPass"](_0x9ebd52);
      const _0x514909 = new OutputPass();
      composer[_0x30cb90(0x7a)](_0x514909),
        composer[_0x30cb90(0x7a)](_0x529a1d),
        (loader = new GLTFLoader()),
        loader["load"](
          _0x30cb90(0x102),
          function (_0x77c503) {
            const _0x5228dc = _0x30cb90;
            (van = _0x77c503[_0x5228dc(0x93)]),
              van[_0x5228dc(0xa1)][_0x5228dc(0xfd)](0xa, 0xa, 0xa),
              scene["add"](van),
              _0x77c503[_0x5228dc(0x93)][_0x5228dc(0xb0)](function (_0x2a15e2) {
                const _0x46dfcb = _0x5228dc;
                if (_0x2a15e2[_0x46dfcb(0xe4)]) {
                  (_0x2a15e2[_0x46dfcb(0xee)] = !![]),
                    (_0x2a15e2[_0x46dfcb(0x113)] = !![]);
                  for (
                    let _0xd93c7e = 0x0;
                    _0xd93c7e < vanElement[_0x46dfcb(0xeb)];
                    _0xd93c7e++
                  ) {
                    if (_0x2a15e2[_0x46dfcb(0xf8)] == vanElement[_0xd93c7e]) {
                      (_0x2a15e2[_0x46dfcb(0x96)]["envMap"] = exrEnv),
                        selects["push"](_0x2a15e2);
                      break;
                    } else {
                      if (_0x2a15e2["name"] != "Color_M00185") {
                        selects[_0x46dfcb(0xd0)](_0x2a15e2),
                          otherMeshes[_0x46dfcb(0xd0)](_0x2a15e2),
                          (_0x2a15e2[_0x46dfcb(0x96)]["envMap"] =
                            cubeRenderTarget[_0x46dfcb(0xc3)]);
                        if (_0x2a15e2[_0x46dfcb(0x96)][_0x46dfcb(0x7e)])
                          _0x2a15e2[_0x46dfcb(0x96)][_0x46dfcb(0x7e)][
                            _0x46dfcb(0xa8)
                          ] = sRGBEncoding;
                        if (_0x2a15e2[_0x46dfcb(0x96)][_0x46dfcb(0x75)])
                          _0x2a15e2[_0x46dfcb(0x96)][_0x46dfcb(0x75)][
                            _0x46dfcb(0xa8)
                          ] = sRGBEncoding;
                        if (
                          _0x2a15e2[_0x46dfcb(0x96)]["map"] ||
                          _0x2a15e2[_0x46dfcb(0x96)][_0x46dfcb(0x75)]
                        )
                          _0x2a15e2[_0x46dfcb(0x96)][_0x46dfcb(0x99)] = !![];
                      }
                    }
                  }
                  (_0x2a15e2[_0x46dfcb(0xf8)] == _0x46dfcb(0xcd) ||
                    _0x2a15e2[_0x46dfcb(0xf8)] == _0x46dfcb(0xd2)) &&
                    (_0x2a15e2[_0x46dfcb(0x104)] = ![]);
                  const _0x2faf85 = new _0x51a658[_0x46dfcb(0xfa)]()[
                    _0x46dfcb(0x89)
                  ](scene);
                  return _0x46e11d[_0x46dfcb(0xa4)](_0x2faf85), _0x2a15e2;
                }
              }),
              cubeCamera[_0x5228dc(0x8f)](renderer, scene);
          },
          undefined,
          function (_0x4416de) {
            const _0x28f285 = _0x30cb90;
            console[_0x28f285(0x94)](_0x4416de);
          }
        ),
        updateEnvironment(),
        cubeCamera[_0x30cb90(0x8f)](renderer, scene);
      const _0x170364 = new GUI();
      _0x170364[_0x30cb90(0xa5)](_0x46e11d, _0x30cb90(0xdb), {
        Default: GTAOPass[_0x30cb90(0xd7)][_0x30cb90(0x8c)],
        Diffuse: GTAOPass[_0x30cb90(0xd7)][_0x30cb90(0x98)],
        "AO\x20Only": GTAOPass["OUTPUT"]["AO"],
        "AO\x20Only\x20+\x20Denoise": GTAOPass["OUTPUT"][_0x30cb90(0x87)],
        Depth: GTAOPass[_0x30cb90(0xd7)]["Depth"],
        Normal: GTAOPass["OUTPUT"][_0x30cb90(0xe7)],
      })[_0x30cb90(0xd9)](function (_0x168109) {
        const _0x2d36ba = _0x30cb90;
        _0x46e11d[_0x2d36ba(0xdb)] = _0x168109;
      });
      const _0x5bb0a4 = {
          radius: 0.2,
          distanceExponent: 1.85,
          thickness: 0x1,
          scale: 1.5,
          samples: 0x20,
          distanceFallOff: 0x1,
          screenSpaceRadius: ![],
        },
        _0x1609eb = {
          lumaPhi: 0xa,
          depthPhi: 0x2,
          normalPhi: 0x3,
          radius: 0.5,
          radiusExponent: 0x1,
          rings: 0x2,
          samples: 0x20,
        };
      _0x46e11d["updateGtaoMaterial"](_0x5bb0a4),
        _0x46e11d[_0x30cb90(0x76)](_0x1609eb),
        _0x170364[_0x30cb90(0xa5)](_0x46e11d, _0x30cb90(0x8b))
          ["min"](0x0)
          ["max"](0x1)
          [_0x30cb90(0x10c)](0.01),
        _0x170364[_0x30cb90(0xa5)](_0x5bb0a4, _0x30cb90(0xcc))
          ["min"](0.01)
          [_0x30cb90(0xff)](0x1)
          [_0x30cb90(0x10c)](0.01)
          [_0x30cb90(0xd9)](() => _0x46e11d[_0x30cb90(0x10f)](_0x5bb0a4)),
        _0x170364[_0x30cb90(0xa5)](_0x5bb0a4, _0x30cb90(0x88))
          ["min"](0x1)
          [_0x30cb90(0xff)](0x4)
          [_0x30cb90(0x10c)](0.01)
          [_0x30cb90(0xd9)](() => _0x46e11d[_0x30cb90(0x10f)](_0x5bb0a4)),
        _0x170364[_0x30cb90(0xa5)](_0x5bb0a4, _0x30cb90(0xc2))
          [_0x30cb90(0xc9)](0.01)
          [_0x30cb90(0xff)](0xa)
          [_0x30cb90(0x10c)](0.01)
          [_0x30cb90(0xd9)](() => _0x46e11d[_0x30cb90(0x10f)](_0x5bb0a4)),
        _0x170364[_0x30cb90(0xa5)](_0x5bb0a4, _0x30cb90(0x111))
          [_0x30cb90(0xc9)](0x0)
          ["max"](0x1)
          [_0x30cb90(0x10c)](0.01)
          ["onChange"](() => _0x46e11d["updateGtaoMaterial"](_0x5bb0a4)),
        _0x170364[_0x30cb90(0xa5)](_0x5bb0a4, _0x30cb90(0xa1))
          [_0x30cb90(0xc9)](0.01)
          ["max"](0x2)
          [_0x30cb90(0x10c)](0.01)
          [_0x30cb90(0xd9)](() => _0x46e11d[_0x30cb90(0x10f)](_0x5bb0a4)),
        _0x170364[_0x30cb90(0xa5)](_0x5bb0a4, _0x30cb90(0x9f))
          ["min"](0x2)
          [_0x30cb90(0xff)](0x20)
          [_0x30cb90(0x10c)](0x1)
          [_0x30cb90(0xd9)](() => _0x46e11d[_0x30cb90(0x10f)](_0x5bb0a4)),
        _0x170364["add"](_0x5bb0a4, _0x30cb90(0xb6))[_0x30cb90(0xd9)](() =>
          _0x46e11d["updateGtaoMaterial"](_0x5bb0a4)
        ),
        _0x170364[_0x30cb90(0xa5)](_0x1609eb, _0x30cb90(0xb9))
          [_0x30cb90(0xc9)](0x0)
          [_0x30cb90(0xff)](0x14)
          [_0x30cb90(0x10c)](0.01)
          [_0x30cb90(0xd9)](() => _0x46e11d[_0x30cb90(0x76)](_0x1609eb)),
        _0x170364[_0x30cb90(0xa5)](_0x1609eb, _0x30cb90(0x78))
          [_0x30cb90(0xc9)](0.01)
          [_0x30cb90(0xff)](0x14)
          ["step"](0.01)
          [_0x30cb90(0xd9)](() => _0x46e11d[_0x30cb90(0x76)](_0x1609eb)),
        _0x170364["add"](_0x1609eb, _0x30cb90(0xd3))
          [_0x30cb90(0xc9)](0.01)
          [_0x30cb90(0xff)](0x14)
          [_0x30cb90(0x10c)](0.01)
          ["onChange"](() => _0x46e11d[_0x30cb90(0x76)](_0x1609eb)),
        _0x170364[_0x30cb90(0xa5)](_0x1609eb, "radius")
          [_0x30cb90(0xc9)](0x0)
          ["max"](0x20)
          ["step"](0x1)
          [_0x30cb90(0xd9)](() => _0x46e11d["updatePdMaterial"](_0x1609eb)),
        _0x170364["add"](_0x1609eb, _0x30cb90(0xf2))
          [_0x30cb90(0xc9)](0.1)
          [_0x30cb90(0xff)](0x4)
          [_0x30cb90(0x10c)](0.1)
          [_0x30cb90(0xd9)](() => _0x46e11d["updatePdMaterial"](_0x1609eb)),
        _0x170364[_0x30cb90(0xa5)](_0x1609eb, "rings")
          [_0x30cb90(0xc9)](0x1)
          [_0x30cb90(0xff)](0x10)
          [_0x30cb90(0x10c)](0.125)
          [_0x30cb90(0xd9)](() => _0x46e11d[_0x30cb90(0x76)](_0x1609eb)),
        _0x170364[_0x30cb90(0xa5)](_0x1609eb, "samples")
          [_0x30cb90(0xc9)](0x2)
          [_0x30cb90(0xff)](0x20)
          [_0x30cb90(0x10c)](0x1)
          [_0x30cb90(0xd9)](() => _0x46e11d[_0x30cb90(0x76)](_0x1609eb)),
        _0x170364["add"](ssrParams, _0x30cb90(0xb1))["name"]("Enable\x20SSR"),
        _0x170364[_0x30cb90(0xa5)](ssrParams, _0x30cb90(0xc6))["onChange"](
          () => {
            const _0xb53034 = _0x30cb90;
            ssrParams[_0xb53034(0xc6)]
              ? ((ssrPass["groundReflector"] = groundReflector),
                (ssrPass[_0xb53034(0x112)] = selects))
              : ((ssrPass["groundReflector"] = null),
                (ssrPass["selects"] = null));
          }
        ),
        (ssrPass[_0x30cb90(0xc2)] = 0.018),
        _0x170364[_0x30cb90(0xa5)](ssrPass, _0x30cb90(0xc2))
          [_0x30cb90(0xc9)](0x0)
          [_0x30cb90(0xff)](0.1)
          [_0x30cb90(0x10c)](0.0001),
        (ssrPass[_0x30cb90(0x9a)] = ![]),
        _0x170364[_0x30cb90(0xa5)](ssrPass, "infiniteThick"),
        _0x170364[_0x30cb90(0xa5)](ssrParams, _0x30cb90(0x83))["onChange"](
          () => {
            const _0xb4f876 = _0x30cb90;
            controls[_0xb4f876(0xa7)] = !ssrParams["autoRotate"];
          }
        );
      const _0x254359 = _0x170364[_0x30cb90(0x92)](_0x30cb90(0xe9));
      _0x254359[_0x30cb90(0xa5)](ssrPass, _0x30cb90(0x9c))["onChange"](() => {
        const _0x61f83b = _0x30cb90;
        groundReflector[_0x61f83b(0x9c)] = ssrPass[_0x61f83b(0x9c)];
      }),
        _0x254359[_0x30cb90(0xa5)](ssrPass, _0x30cb90(0x7f))[_0x30cb90(0xd9)](
          () => {
            const _0x1a443b = _0x30cb90;
            groundReflector[_0x1a443b(0x7f)] = ssrPass["distanceAttenuation"];
          }
        ),
        (ssrPass[_0x30cb90(0xdc)] = 0.3),
        (groundReflector[_0x30cb90(0xdc)] = ssrPass[_0x30cb90(0xdc)]),
        _0x254359[_0x30cb90(0xa5)](ssrPass, _0x30cb90(0xdc))
          [_0x30cb90(0xc9)](0x0)
          [_0x30cb90(0xff)](0.5)
          [_0x30cb90(0x10c)](0.001)
          [_0x30cb90(0xd9)](() => {
            const _0x332b2b = _0x30cb90;
            groundReflector[_0x332b2b(0xdc)] = ssrPass["maxDistance"];
          }),
        _0x254359[_0x30cb90(0xa5)](ssrParams, "otherMeshes")[_0x30cb90(0xd9)](
          () => {
            const _0x2734f6 = _0x30cb90;
            ssrParams[_0x2734f6(0xc4)]
              ? otherMeshes[_0x2734f6(0xa0)](
                  (_0x18d5e5) => (_0x18d5e5["visible"] = !![])
                )
              : otherMeshes["forEach"](
                  (_0x377d29) => (_0x377d29[_0x2734f6(0x104)] = ![])
                );
          }
        ),
        _0x254359["add"](ssrPass, _0x30cb90(0x91)),
        _0x254359[_0x30cb90(0xa5)](ssrPass, _0x30cb90(0xdb), {
          Default: SSRPass[_0x30cb90(0xd7)][_0x30cb90(0x8c)],
          "SSR\x20Only": SSRPass["OUTPUT"]["SSR"],
          Beauty: SSRPass[_0x30cb90(0xd7)][_0x30cb90(0x101)],
          Depth: SSRPass["OUTPUT"][_0x30cb90(0x8a)],
          Normal: SSRPass[_0x30cb90(0xd7)][_0x30cb90(0xe7)],
          Metalness: SSRPass[_0x30cb90(0xd7)][_0x30cb90(0xf9)],
        })[_0x30cb90(0xd9)](function (_0x4e274b) {
          const _0x273832 = _0x30cb90;
          ssrPass[_0x273832(0xdb)] = _0x4e274b;
        }),
        (ssrPass[_0x30cb90(0x72)] = 0.5),
        (groundReflector["opacity"] = ssrPass[_0x30cb90(0x72)]),
        _0x254359[_0x30cb90(0xa5)](ssrPass, _0x30cb90(0x72))
          [_0x30cb90(0xc9)](0x0)
          [_0x30cb90(0xff)](0x1)
          [_0x30cb90(0xd9)](() => {
            groundReflector["opacity"] = ssrPass["opacity"];
          }),
        _0x254359[_0x30cb90(0xa5)](ssrPass, "blur"),
        _0x170364[_0x30cb90(0xaa)](),
        _0x170364["hide"](),
        controls[_0x30cb90(0xd1)](_0x30cb90(0x85), () => {
          const _0x59f375 = _0x30cb90;
          console[_0x59f375(0x9d)](
            "camera\x20position:\x20",
            camera["position"]
          ),
            console[_0x59f375(0x9d)](
              "controls\x20target:\x20",
              controls[_0x59f375(0xed)]
            );
        });
    },
    updateEnvironment = () => {
      const _0x475d76 = _0xfa8a43,
        _0x179c25 = environments["filter"](
          (_0x2a1ca9) => _0x2a1ca9["name"] === initialState["environment"]
        )[0x0];
      console[_0x475d76(0x9d)]("environment:\x20", _0x179c25),
        getCubeMapTexture(_0x179c25)[_0x475d76(0xdd)](
          ({ envMap: _0x23fc94 }) => {
            exrEnv = _0x23fc94;
          }
        );
    },
    getCubeMapTexture = (_0x8f465c) => {
      const _0x3960a9 = _0xfa8a43,
        { id: _0x275ea7, path: _0xb0d3a8 } = _0x8f465c;
      if (_0x275ea7 === _0x3960a9(0xde))
        return Promise[_0x3960a9(0x110)]({ envMap: neutralEnvironment });
      if (_0x275ea7 === "") return Promise["resolve"]({ envMap: null });
      return new Promise((_0x265dc9, _0x30003a) => {
        const _0x38f584 = _0x3960a9;
        new EXRLoader()[_0x38f584(0xf7)](
          _0xb0d3a8,
          (_0xdedd90) => {
            const _0x28d0a6 = _0x38f584,
              _0x37390d = pmremGenerator[_0x28d0a6(0xe8)](_0xdedd90)["texture"];
            pmremGenerator["dispose"](),
              console["log"]("envMap:\x20", _0x37390d),
              _0x265dc9({ envMap: _0x37390d });
          },
          undefined,
          _0x30003a
        );
      });
    },
    animate = () => {
      const _0x370665 = _0xfa8a43;
      requestAnimationFrame(animate),
        controls[_0x370665(0x8f)](),
        TWEEN[_0x370665(0x8f)](),
        ssrParams[_0x370665(0xb1)]
          ? composer[_0x370665(0x84)]()
          : renderer["render"](scene, camera);
    };
  function onWindowResize() {
    const _0x5b67d8 = _0xfa8a43,
      _0x46321e = window["innerWidth"],
      _0x1ee79d = window["innerHeight"];
    camera[_0x5b67d8(0xec)](),
      renderer[_0x5b67d8(0xe5)](_0x46321e, _0x1ee79d),
      composer[_0x5b67d8(0xe5)](_0x46321e, _0x1ee79d),
      groundReflector["getRenderTarget"]()[_0x5b67d8(0xe5)](
        _0x46321e,
        _0x1ee79d
      ),
      groundReflector[_0x5b67d8(0x79)][_0x5b67d8(0xfd)](_0x46321e, _0x1ee79d);
  }
  const onOverViewButton = () => {
    const _0x43274e = _0xfa8a43;
    isGoMallMode = !isGoMallMode;
    if (isGoMallMode) {
      textButtonView = _0x43274e(0x70);
      let _0x13e016 = {
        x: camera[_0x43274e(0xc8)]["x"],
        y: camera["position"]["y"],
        z: camera["position"]["z"],
      };
      new TWEEN[_0x43274e(0x117)](_0x13e016)
        ["to"]({
          x: 0.33266818379163465,
          y: 0.4567208098842309,
          z: 0.009396602938231524,
        })
        [_0x43274e(0xe6)](() => {
          const _0x528d06 = _0x43274e;
          return (
            controls[_0x528d06(0xed)][_0x528d06(0xfd)](
              -0.18035187854860613,
              0.34989708000472913,
              0.014436166392607084
            ),
            camera[_0x528d06(0xc8)][_0x528d06(0xc5)](_0x13e016)
          );
        })
        [_0x43274e(0xf1)]();
    } else {
      textButtonView = "View\x20Mode";
      let _0x536d5b = {
        x: camera["position"]["x"],
        y: camera["position"]["y"],
        z: camera[_0x43274e(0xc8)]["z"],
      };
      new TWEEN[_0x43274e(0x117)](_0x536d5b)
        ["to"]({ x: 0x0, y: 0x3, z: -0x1 })
        [_0x43274e(0xe6)](() => {
          const _0x5491fc = _0x43274e;
          return (
            controls["target"]["set"](0x0, 0x0, 0x0),
            camera[_0x5491fc(0xc8)]["copy"](_0x536d5b)
          );
        })
        [_0x43274e(0xf1)]();
    }
  };
  onMount(() => {
    const _0x551242 = _0xfa8a43;
    init(), animate(), window[_0x551242(0xd1)](_0x551242(0xf3), onWindowResize);
  });
</script>

<main>
  <div class="view-button">
    <button
      style="--focus-color: {isGoMallMode ? '#1d6291' : '#006db6'}; "
      on:click={onOverViewButton}>{textButtonView}</button
    >
  </div>

  <canvas class="full-screen" id="container" bind:this={canvas}> </canvas>
</main>

<!-- on:click={getDetailModel} -->

<style>
  .full-screen {
    margin: 0 !important;
    padding: 0 !important;
  }

  .view-button {
    left: 50%;
    position: absolute;
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
