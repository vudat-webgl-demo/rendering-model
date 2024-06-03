<script>
  const _0x17dd9c = _0x165e;
  (function (_0x28e0e6, _0x5f461b) {
    const _0x212284 = _0x165e,
      _0x190a46 = _0x28e0e6();
    while (!![]) {
      try {
        const _0x5c8fa1 =
          (-parseInt(_0x212284(0xb5)) / 0x1) *
            (-parseInt(_0x212284(0x98)) / 0x2) +
          -parseInt(_0x212284(0x8c)) / 0x3 +
          (-parseInt(_0x212284(0x8d)) / 0x4) *
            (-parseInt(_0x212284(0xa0)) / 0x5) +
          parseInt(_0x212284(0x9e)) / 0x6 +
          -parseInt(_0x212284(0x123)) / 0x7 +
          (-parseInt(_0x212284(0xb2)) / 0x8) *
            (-parseInt(_0x212284(0x128)) / 0x9) +
          (parseInt(_0x212284(0x131)) / 0xa) *
            (parseInt(_0x212284(0x12b)) / 0xb);
        if (_0x5c8fa1 === _0x5f461b) break;
        else _0x190a46["push"](_0x190a46["shift"]());
      } catch (_0x290502) {
        _0x190a46["push"](_0x190a46["shift"]());
      }
    }
  })(_0x4d0e, 0xda82a);
  function _0x165e(_0x226909, _0x480118) {
    const _0x4d0e2e = _0x4d0e();
    return (
      (_0x165e = function (_0x165e64, _0x47f840) {
        _0x165e64 = _0x165e64 - 0x84;
        let _0x4a69a8 = _0x4d0e2e[_0x165e64];
        return _0x4a69a8;
      }),
      _0x165e(_0x226909, _0x480118)
    );
  }
  import * as _0x1fb42a from "../build/three.module";
  import { onMount, tick } from "svelte";
  import { GLTFLoader } from "../js/GLTFLoader";
  import { OrbitControls } from "../js/OrbitControls";
  import { TWEEN } from "../js/tween.module.min.js";
  import { EXRLoader } from "../js/EXRLoader.js";
  import { environments } from "../public/assets/environment/index.js";
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
  function _0x4d0e() {
    const _0x2527a8 = [
      "WebGLCubeRenderTarget",
      "RGBAFormat",
      "resolve",
      "Denoise",
      "MeshBasicMaterial",
      "click\x20detail",
      "enableSSR",
      "Color_M00185",
      "./assets/models/van/van2.glb",
      "resolution",
      "then",
      "Color_M00136",
      "radiusExponent",
      "Default_150150150008",
      "Color_M00158",
      "updateProjectionMatrix",
      "addFolder",
      "forEach",
      "castShadow",
      "getRenderTarget",
      "includes",
      "PerspectiveCamera",
      "scale",
      "dispose",
      "blendIntensity",
      "step",
      "depthPhi",
      "pano_d",
      "View\x20Mode",
      "envMap:\x20",
      "log",
      "Default_150150150004",
      "cos",
      "uniforms",
      "Raycaster",
      "Color_M00181",
      "lumaPhi",
      "Beauty",
      "Home\x20Mode",
      "click\x20Object:\x20",
      "Default",
      "thickness",
      "PointLight",
      "near",
      "environ:\x20",
      "Color_M00426",
      "traverse",
      "physicallyCorrectLights",
      "copy",
      "SSR",
      "OUTPUT",
      "bias",
      "Scene",
      "receiveShadow",
      "resize",
      "Color_M00169",
      "Color",
      "distanceAttenuation",
      "set",
      "opacity",
      "pano_l",
      "clientX",
      "setFromObject",
      "setClearColor",
      "maxDistance",
      "ambient_light",
      "fromScene",
      "push",
      "offsetWidth",
      "innerWidth",
      "PlaneGeometry",
      "compileEquirectangularShader",
      "Metalness",
      "right",
      "shadowMap",
      "envMap",
      "sin",
      "Enable\x20SSR",
      "name",
      "setSize",
      "update",
      "onUpdate",
      "Color_M00176",
      "error",
      "start",
      "texture",
      "add",
      "LinearMipmapLinearFilter",
      "intersectObjects",
      "Color_M00170",
      "shadow",
      "max",
      "selects",
      "camera",
      "DirectionalLight",
      "390187rhnMJj",
      "addPass",
      "otherMeshes",
      "infiniteThick",
      "enabled",
      "88848OtthHv",
      "change",
      "Forest",
      "11iUWumj",
      "onChange",
      "pano_f",
      "more\x20settings",
      "depthWrite",
      "filter",
      "1077170ubBoIo",
      "updatePdMaterial",
      "position",
      "ACESFilmicToneMapping",
      "output",
      "rotation",
      "rings",
      "BoxGeometry",
      "close",
      "innerHeight",
      "width",
      "fromEquirectangular",
      "updateGtaoMaterial",
      "samples",
      "top",
      "mapSize",
      "neutral",
      "5225280NndPVo",
      "2868hTIMOu",
      "Color_M00127",
      "Color_M00173",
      "setFromCamera",
      "addEventListener",
      "distanceExponent",
      "offsetHeight",
      "groundReflector",
      "Color_M00381",
      "Vector2",
      "Depth",
      "62CNAntm",
      "type",
      "Color_M00210",
      "clientY",
      "AmbientLight",
      "min",
      "8999208ByGVjH",
      "toneMapping",
      "2605xGjonR",
      ".jpg",
      "enableDamping",
      "point",
      "PCFShadowMap",
      "visible",
      "fresnel",
      "material",
      "Color_M00149",
      "screenSpaceRadius",
      "Normal",
      "WebGLRenderer",
      "normalPhi",
      "target",
      "autoRotate",
      "Mesh",
      "domElement",
      "render",
      "472gSksQH",
      "bouncing",
      "Color_M00135",
      "4159RuSRTw",
      "value",
      "Tween",
      "pano_r",
      "coordinate:\x20",
      "CubeCamera",
      "radius",
      "object",
      "Color_M00269",
      "children",
      "envMapIntensity",
      "setPixelRatio",
      "isMesh",
      "pano_b",
      "length",
    ];
    _0x4d0e = function () {
      return _0x2527a8;
    };
    return _0x4d0e();
  }
  const selects = [];
  let initialState = { environment: _0x17dd9c(0x12a), background: ![] },
    pmremCubeRenderTarget,
    internalEnvMap;
  const widthScreen = window["innerWidth"],
    heightScreen = window[_0x17dd9c(0x84)],
    SHADOW_MAP_WIDTH = 0x800,
    SHADOW_MAP_HEIGHT = 0x400,
    outSideVanElement = [
      "Color_M00168",
      _0x17dd9c(0xd2),
      _0x17dd9c(0xcf),
      _0x17dd9c(0xe7),
      "Color_M00197",
      _0x17dd9c(0xd1),
      _0x17dd9c(0x9a),
      _0x17dd9c(0x8f),
      _0x17dd9c(0x116),
      _0x17dd9c(0x8e),
      _0x17dd9c(0xf1),
      _0x17dd9c(0xe3),
      _0x17dd9c(0xfb),
      _0x17dd9c(0x11d),
      _0x17dd9c(0xa8),
      "Color_M00135",
      "Color_M00426",
      _0x17dd9c(0x95),
    ],
    noSelectSSR = [
      _0x17dd9c(0xcb),
      "Color_M00264",
      "Color_M00066",
      _0x17dd9c(0xbd),
      "Color_M00265",
    ];
  let mouse = new _0x1fb42a[_0x17dd9c(0x96)](),
    raycaster = new _0x1fb42a[_0x17dd9c(0xe6)](),
    isGoMallMode = ![],
    textButtonView = _0x17dd9c(0xe0);
  const init = () => {
      const _0x430ce4 = _0x17dd9c;
      let _0x2243fc = "src/assets/cube-screen/",
        _0x18fa67 = _0x430ce4(0xa1),
        _0x537ceb = [
          _0x2243fc + _0x430ce4(0xb8) + _0x18fa67,
          _0x2243fc + _0x430ce4(0x100) + _0x18fa67,
          _0x2243fc + "pano_u" + _0x18fa67,
          _0x2243fc + _0x430ce4(0xdf) + _0x18fa67,
          _0x2243fc + _0x430ce4(0x12d) + _0x18fa67,
          _0x2243fc + _0x430ce4(0xc2) + _0x18fa67,
        ];
      (camera = new _0x1fb42a[_0x430ce4(0xd9)](
        0x4b,
        widthScreen / heightScreen,
        0.1,
        0x64
      )),
        camera["position"][_0x430ce4(0xfe)](0x0, 0x3, -0x1),
        (scene = new _0x1fb42a[_0x430ce4(0xf8)]()),
        (scene["background"] = new _0x1fb42a[_0x430ce4(0xfc)](0xcccccc)),
        (clock = new _0x1fb42a["Clock"]()),
        scene[_0x430ce4(0x11a)](camera);
      const _0x5a76e1 = new _0x1fb42a[_0x430ce4(0x9c)](0xffffff, 0.5);
      (_0x5a76e1[_0x430ce4(0x112)] = _0x430ce4(0x105)),
        scene[_0x430ce4(0x11a)](_0x5a76e1);
      const _0x139772 = new _0x1fb42a[_0x430ce4(0x122)](
        0xffffff,
        0.8 * Math["PI"]
      );
      (_0x139772[_0x430ce4(0xd6)] = !![]),
        (_0x139772[_0x430ce4(0x11e)][_0x430ce4(0x121)][_0x430ce4(0x89)] =
          0x7d0),
        (_0x139772[_0x430ce4(0x11e)][_0x430ce4(0x121)]["bottom"] = -0x7d0),
        (_0x139772[_0x430ce4(0x11e)][_0x430ce4(0x121)]["left"] = -0x7d0),
        (_0x139772[_0x430ce4(0x11e)][_0x430ce4(0x121)][_0x430ce4(0x10d)] =
          0x7d0),
        (_0x139772[_0x430ce4(0x11e)][_0x430ce4(0x121)][_0x430ce4(0xef)] =
          0x4b0),
        (_0x139772[_0x430ce4(0x11e)][_0x430ce4(0x121)]["far"] = 0x9c4),
        (_0x139772[_0x430ce4(0x11e)][_0x430ce4(0xf7)] = 0.0001),
        (_0x139772[_0x430ce4(0x11e)][_0x430ce4(0x8a)][_0x430ce4(0x85)] =
          SHADOW_MAP_WIDTH),
        (_0x139772[_0x430ce4(0x11e)][_0x430ce4(0x8a)]["height"] =
          SHADOW_MAP_HEIGHT),
        scene[_0x430ce4(0x11a)](_0x139772),
        (renderer = new _0x1fb42a[_0x430ce4(0xab)]({
          canvas: canvas,
          antialias: !![],
        })),
        (renderer[_0x430ce4(0xf3)] = !![]),
        (renderer["outputEncoding"] = sRGBEncoding),
        renderer[_0x430ce4(0x103)](0xcccccc),
        renderer[_0x430ce4(0xc0)](window["devicePixelRatio"]),
        renderer["setSize"](widthScreen, heightScreen),
        (renderer[_0x430ce4(0x9f)] = _0x1fb42a[_0x430ce4(0x134)]),
        (renderer["toneMappingExposure"] = 1.2),
        (renderer[_0x430ce4(0x10e)][_0x430ce4(0x127)] = !![]),
        (renderer[_0x430ce4(0x10e)][_0x430ce4(0x99)] =
          _0x1fb42a[_0x430ce4(0xa4)]),
        (cubeRenderTarget = new _0x1fb42a[_0x430ce4(0xc4)](0x800, {
          format: _0x1fb42a[_0x430ce4(0xc5)],
          generateMipmaps: !![],
          minFilter: _0x1fb42a[_0x430ce4(0x11b)],
          encoding: _0x1fb42a["sRGBEncoding"],
        })),
        (cubeCamera = new _0x1fb42a[_0x430ce4(0xba)](
          0x1,
          0x2710,
          cubeRenderTarget
        )),
        cubeCamera[_0x430ce4(0xda)]["set"](0.1, 0.1, 0.1),
        cubeCamera[_0x430ce4(0x133)][_0x430ce4(0xfe)](-0.3, 0.65, 0x0);
      const _0x216f95 = new _0x1fb42a[_0x430ce4(0x138)](0x1, 0x1, 0x1),
        _0xae0711 = new _0x1fb42a[_0x430ce4(0xc8)]({ color: 0xff00 }),
        _0x244443 = new _0x1fb42a[_0x430ce4(0xaf)](_0x216f95, _0xae0711);
      _0x244443[_0x430ce4(0x133)][_0x430ce4(0xfe)](-0.3, 0.65, 0x0);
      let _0x32e449 = new _0x1fb42a[_0x430ce4(0x10a)](0x19, 0x19);
      (groundReflector = new ReflectorForSSRPass(_0x32e449, {
        clipBias: 0.0003,
        textureWidth: window[_0x430ce4(0x109)],
        textureHeight: window["innerHeight"],
        color: 0x888888,
        useDepthTexture: !![],
      })),
        (groundReflector["material"][_0x430ce4(0x12f)] = ![]),
        (groundReflector[_0x430ce4(0x136)]["x"] = -Math["PI"] / 0x2),
        (groundReflector[_0x430ce4(0xa5)] = ![]),
        cubeCamera[_0x430ce4(0x114)](renderer, scene),
        (pmremGenerator = new _0x1fb42a["PMREMGenerator"](renderer)),
        pmremGenerator[_0x430ce4(0x10b)](),
        (pmremCubeRenderTarget = pmremGenerator["fromEquirectangular"](
          cubeRenderTarget[_0x430ce4(0x119)]
        )),
        (internalEnvMap = pmremCubeRenderTarget?.[_0x430ce4(0x119)]),
        (neutralEnvironment = pmremGenerator[_0x430ce4(0x106)](
          new RoomEnvironment()
        )[_0x430ce4(0x119)]),
        (controls = new OrbitControls(camera, renderer[_0x430ce4(0xb0)])),
        (controls[_0x430ce4(0x127)] = !![]),
        (controls[_0x430ce4(0xa2)] = !![]),
        (controls["dampingFactor"] = 0.5),
        (composer = new EffectComposer(renderer));
      const _0xe3e16e = new RenderPass(scene, camera);
      composer[_0x430ce4(0x124)](_0xe3e16e);
      const _0xbd48e = new GTAOPass(scene, camera, widthScreen, heightScreen);
      (_0xbd48e[_0x430ce4(0x135)] = GTAOPass["OUTPUT"][_0x430ce4(0xec)]),
        (ssrPass = new SSRPass({
          renderer: renderer,
          scene: scene,
          camera: camera,
          width: widthScreen,
          height: heightScreen,
          groundReflector: ssrParams[_0x430ce4(0x94)] ? groundReflector : null,
          selects: ssrParams[_0x430ce4(0x94)] ? selects : null,
        })),
        composer[_0x430ce4(0x124)](ssrPass),
        composer["addPass"](_0xbd48e);
      const _0x16a78f = new ShaderPass(FXAAShader),
        _0x53a701 = renderer["getPixelRatio"]();
      (_0x16a78f[_0x430ce4(0xa7)][_0x430ce4(0xe5)][_0x430ce4(0xcd)][
        _0x430ce4(0xb6)
      ]["x"] = 0x1 / (canvas[_0x430ce4(0x108)] * _0x53a701)),
        (_0x16a78f[_0x430ce4(0xa7)]["uniforms"][_0x430ce4(0xcd)][
          _0x430ce4(0xb6)
        ]["y"] = 0x1 / (canvas[_0x430ce4(0x93)] * _0x53a701));
      const _0x1c21bf = new ShaderPass(GammaCorrectionShader);
      composer[_0x430ce4(0x124)](_0x1c21bf);
      const _0x3c0aa9 = new OutputPass();
      composer[_0x430ce4(0x124)](_0x3c0aa9),
        composer["addPass"](_0x16a78f),
        (loader = new GLTFLoader()),
        loader["load"](
          _0x430ce4(0xcc),
          function (_0x10c0ac) {
            const _0xb8e6ab = _0x430ce4;
            (van = _0x10c0ac["scene"]),
              van[_0xb8e6ab(0xda)][_0xb8e6ab(0xfe)](0xa, 0xa, 0xa),
              scene[_0xb8e6ab(0x11a)](van),
              _0x10c0ac["scene"][_0xb8e6ab(0xf2)](function (_0x432940) {
                const _0x125e5e = _0xb8e6ab;
                if (_0x432940[_0x125e5e(0xc1)]) {
                  (_0x432940["castShadow"] = !![]),
                    (_0x432940[_0x125e5e(0xf9)] = !![]);
                  if (
                    noSelectSSR[_0x125e5e(0xd8)](_0x432940[_0x125e5e(0x112)])
                  ) {
                  } else
                    outSideVanElement["includes"](_0x432940[_0x125e5e(0x112)])
                      ? ((_0x432940[_0x125e5e(0xa7)]["envMap"] = exrEnv),
                        selects[_0x125e5e(0x107)](_0x432940))
                      : ((_0x432940[_0x125e5e(0xa7)][_0x125e5e(0x10f)] =
                          cubeRenderTarget[_0x125e5e(0x119)]),
                        (_0x432940["material"][_0x125e5e(0xbf)] = 0.35),
                        (_0x432940["material"]["needsUpdate"] = !![]),
                        selects[_0x125e5e(0x107)](_0x432940));
                  (_0x432940[_0x125e5e(0x112)] == _0x125e5e(0xb4) ||
                    _0x432940[_0x125e5e(0x112)] == "Color_M00426") &&
                    (_0x432940[_0x125e5e(0xa5)] = ![]);
                  const _0x4541c4 = new _0x1fb42a["Box3"]()[_0x125e5e(0x102)](
                    scene
                  );
                  _0xbd48e["setSceneClipBox"](_0x4541c4);
                }
              }),
              cubeCamera[_0xb8e6ab(0x114)](renderer, scene);
          },
          undefined,
          function (_0x4f5e61) {
            const _0x2e08c7 = _0x430ce4;
            console[_0x2e08c7(0x117)](_0x4f5e61);
          }
        ),
        updateEnvironment(),
        cubeCamera[_0x430ce4(0x114)](renderer, scene);
      const _0x5919e7 = new GUI();
      _0x5919e7[_0x430ce4(0x11a)](_0xbd48e, _0x430ce4(0x135), {
        Default: GTAOPass[_0x430ce4(0xf6)][_0x430ce4(0xec)],
        Diffuse: GTAOPass[_0x430ce4(0xf6)]["Diffuse"],
        "AO\x20Only": GTAOPass[_0x430ce4(0xf6)]["AO"],
        "AO\x20Only\x20+\x20Denoise":
          GTAOPass[_0x430ce4(0xf6)][_0x430ce4(0xc7)],
        Depth: GTAOPass[_0x430ce4(0xf6)][_0x430ce4(0x97)],
        Normal: GTAOPass[_0x430ce4(0xf6)]["Normal"],
      })[_0x430ce4(0x12c)](function (_0x36e530) {
        const _0x2a2bb0 = _0x430ce4;
        _0xbd48e[_0x2a2bb0(0x135)] = _0x36e530;
      });
      const _0x25a457 = {
          radius: 0.2,
          distanceExponent: 1.85,
          thickness: 0.5,
          scale: 1.5,
          samples: 0x20,
          distanceFallOff: 0x1,
          screenSpaceRadius: ![],
        },
        _0x474a4d = {
          lumaPhi: 0xa,
          depthPhi: 0x2,
          normalPhi: 0x3,
          radius: 0.5,
          radiusExponent: 0x1,
          rings: 0x2,
          samples: 0x20,
        };
      _0xbd48e[_0x430ce4(0x87)](_0x25a457),
        _0xbd48e["updatePdMaterial"](_0x474a4d),
        _0x5919e7[_0x430ce4(0x11a)](_0xbd48e, _0x430ce4(0xdc))
          [_0x430ce4(0x9d)](0x0)
          ["max"](0x1)
          [_0x430ce4(0xdd)](0.01),
        _0x5919e7["add"](_0x25a457, _0x430ce4(0xbb))
          [_0x430ce4(0x9d)](0.01)
          [_0x430ce4(0x11f)](0x1)
          [_0x430ce4(0xdd)](0.01)
          [_0x430ce4(0x12c)](() => _0xbd48e[_0x430ce4(0x87)](_0x25a457)),
        _0x5919e7["add"](_0x25a457, _0x430ce4(0x92))
          [_0x430ce4(0x9d)](0x1)
          ["max"](0x4)
          [_0x430ce4(0xdd)](0.01)
          [_0x430ce4(0x12c)](() => _0xbd48e[_0x430ce4(0x87)](_0x25a457)),
        _0x5919e7["add"](_0x25a457, _0x430ce4(0xed))
          [_0x430ce4(0x9d)](0.01)
          [_0x430ce4(0x11f)](0xa)
          [_0x430ce4(0xdd)](0.01)
          [_0x430ce4(0x12c)](() => _0xbd48e[_0x430ce4(0x87)](_0x25a457)),
        _0x5919e7[_0x430ce4(0x11a)](_0x25a457, "distanceFallOff")
          [_0x430ce4(0x9d)](0x0)
          [_0x430ce4(0x11f)](0x1)
          [_0x430ce4(0xdd)](0.01)
          ["onChange"](() => _0xbd48e["updateGtaoMaterial"](_0x25a457)),
        _0x5919e7[_0x430ce4(0x11a)](_0x25a457, _0x430ce4(0xda))
          ["min"](0.01)
          ["max"](0x2)
          [_0x430ce4(0xdd)](0.01)
          [_0x430ce4(0x12c)](() => _0xbd48e[_0x430ce4(0x87)](_0x25a457)),
        _0x5919e7["add"](_0x25a457, _0x430ce4(0x88))
          [_0x430ce4(0x9d)](0x2)
          [_0x430ce4(0x11f)](0x20)
          [_0x430ce4(0xdd)](0x1)
          [_0x430ce4(0x12c)](() => _0xbd48e[_0x430ce4(0x87)](_0x25a457)),
        _0x5919e7[_0x430ce4(0x11a)](_0x25a457, _0x430ce4(0xa9))[
          _0x430ce4(0x12c)
        ](() => _0xbd48e[_0x430ce4(0x87)](_0x25a457)),
        _0x5919e7["add"](_0x474a4d, _0x430ce4(0xe8))
          [_0x430ce4(0x9d)](0x0)
          [_0x430ce4(0x11f)](0x14)
          ["step"](0.01)
          [_0x430ce4(0x12c)](() => _0xbd48e["updatePdMaterial"](_0x474a4d)),
        _0x5919e7["add"](_0x474a4d, _0x430ce4(0xde))
          [_0x430ce4(0x9d)](0.01)
          [_0x430ce4(0x11f)](0x14)
          [_0x430ce4(0xdd)](0.01)
          ["onChange"](() => _0xbd48e["updatePdMaterial"](_0x474a4d)),
        _0x5919e7["add"](_0x474a4d, _0x430ce4(0xac))
          [_0x430ce4(0x9d)](0.01)
          [_0x430ce4(0x11f)](0x14)
          [_0x430ce4(0xdd)](0.01)
          [_0x430ce4(0x12c)](() => _0xbd48e["updatePdMaterial"](_0x474a4d)),
        _0x5919e7["add"](_0x474a4d, _0x430ce4(0xbb))
          [_0x430ce4(0x9d)](0x0)
          [_0x430ce4(0x11f)](0x20)
          [_0x430ce4(0xdd)](0x1)
          [_0x430ce4(0x12c)](() => _0xbd48e["updatePdMaterial"](_0x474a4d)),
        _0x5919e7[_0x430ce4(0x11a)](_0x474a4d, _0x430ce4(0xd0))
          [_0x430ce4(0x9d)](0.1)
          ["max"](0x4)
          ["step"](0.1)
          [_0x430ce4(0x12c)](() => _0xbd48e[_0x430ce4(0x132)](_0x474a4d)),
        _0x5919e7[_0x430ce4(0x11a)](_0x474a4d, _0x430ce4(0x137))
          [_0x430ce4(0x9d)](0x1)
          [_0x430ce4(0x11f)](0x10)
          [_0x430ce4(0xdd)](0.125)
          [_0x430ce4(0x12c)](() => _0xbd48e["updatePdMaterial"](_0x474a4d)),
        _0x5919e7[_0x430ce4(0x11a)](_0x474a4d, "samples")
          ["min"](0x2)
          [_0x430ce4(0x11f)](0x20)
          [_0x430ce4(0xdd)](0x1)
          [_0x430ce4(0x12c)](() => _0xbd48e[_0x430ce4(0x132)](_0x474a4d)),
        _0x5919e7[_0x430ce4(0x11a)](ssrParams, "enableSSR")[_0x430ce4(0x112)](
          _0x430ce4(0x111)
        ),
        _0x5919e7["add"](ssrParams, _0x430ce4(0x94))[_0x430ce4(0x12c)](() => {
          const _0x503f3f = _0x430ce4;
          ssrParams[_0x503f3f(0x94)]
            ? ((ssrPass[_0x503f3f(0x94)] = groundReflector),
              (ssrPass[_0x503f3f(0x120)] = selects))
            : ((ssrPass[_0x503f3f(0x94)] = null),
              (ssrPass[_0x503f3f(0x120)] = null));
        }),
        (ssrPass[_0x430ce4(0xed)] = 0.018),
        _0x5919e7[_0x430ce4(0x11a)](ssrPass, _0x430ce4(0xed))
          [_0x430ce4(0x9d)](0x0)
          [_0x430ce4(0x11f)](0.1)
          [_0x430ce4(0xdd)](0.0001),
        (ssrPass["infiniteThick"] = ![]),
        _0x5919e7["add"](ssrPass, _0x430ce4(0x126)),
        _0x5919e7["add"](ssrParams, _0x430ce4(0xae))[_0x430ce4(0x12c)](() => {
          const _0x23c63f = _0x430ce4;
          controls[_0x23c63f(0x127)] = !ssrParams[_0x23c63f(0xae)];
        });
      const _0x339732 = _0x5919e7[_0x430ce4(0xd4)](_0x430ce4(0x12e));
      _0x339732[_0x430ce4(0x11a)](ssrPass, _0x430ce4(0xa6))[_0x430ce4(0x12c)](
        () => {
          const _0xdc1470 = _0x430ce4;
          groundReflector[_0xdc1470(0xa6)] = ssrPass[_0xdc1470(0xa6)];
        }
      ),
        _0x339732[_0x430ce4(0x11a)](ssrPass, _0x430ce4(0xfd))[_0x430ce4(0x12c)](
          () => {
            const _0x56d889 = _0x430ce4;
            groundReflector[_0x56d889(0xfd)] = ssrPass[_0x56d889(0xfd)];
          }
        ),
        (ssrPass["maxDistance"] = 0.22),
        (groundReflector[_0x430ce4(0x104)] = ssrPass["maxDistance"]),
        _0x339732[_0x430ce4(0x11a)](ssrPass, _0x430ce4(0x104))
          [_0x430ce4(0x9d)](0x0)
          [_0x430ce4(0x11f)](0.5)
          [_0x430ce4(0xdd)](0.001)
          [_0x430ce4(0x12c)](() => {
            const _0x2023c8 = _0x430ce4;
            groundReflector[_0x2023c8(0x104)] = ssrPass["maxDistance"];
          }),
        _0x339732[_0x430ce4(0x11a)](ssrParams, "otherMeshes")["onChange"](
          () => {
            const _0x16e821 = _0x430ce4;
            ssrParams[_0x16e821(0x125)]
              ? otherMeshes[_0x16e821(0xd5)](
                  (_0x36712d) => (_0x36712d[_0x16e821(0xa5)] = !![])
                )
              : otherMeshes["forEach"](
                  (_0x523d40) => (_0x523d40["visible"] = ![])
                );
          }
        ),
        _0x339732[_0x430ce4(0x11a)](ssrPass, _0x430ce4(0xb3)),
        _0x339732["add"](ssrPass, _0x430ce4(0x135), {
          Default: SSRPass["OUTPUT"]["Default"],
          "SSR\x20Only": SSRPass[_0x430ce4(0xf6)][_0x430ce4(0xf5)],
          Beauty: SSRPass[_0x430ce4(0xf6)][_0x430ce4(0xe9)],
          Depth: SSRPass["OUTPUT"]["Depth"],
          Normal: SSRPass[_0x430ce4(0xf6)][_0x430ce4(0xaa)],
          Metalness: SSRPass[_0x430ce4(0xf6)][_0x430ce4(0x10c)],
        })[_0x430ce4(0x12c)](function (_0x424e1c) {
          const _0x1980a0 = _0x430ce4;
          ssrPass[_0x1980a0(0x135)] = _0x424e1c;
        }),
        (ssrPass[_0x430ce4(0xff)] = 0.5),
        (groundReflector[_0x430ce4(0xff)] = ssrPass[_0x430ce4(0xff)]),
        _0x339732["add"](ssrPass, _0x430ce4(0xff))
          [_0x430ce4(0x9d)](0x0)
          [_0x430ce4(0x11f)](0x1)
          [_0x430ce4(0x12c)](() => {
            const _0x3d5e44 = _0x430ce4;
            groundReflector["opacity"] = ssrPass[_0x3d5e44(0xff)];
          }),
        _0x339732[_0x430ce4(0x11a)](ssrPass, "blur"),
        _0x5919e7[_0x430ce4(0x139)](),
        controls[_0x430ce4(0x91)](_0x430ce4(0x129), () => {});
    },
    createGlowEffect = (
      _0xaaa0b9,
      _0x303af8,
      _0x57a217,
      _0x280cd2,
      _0x3a7d7b,
      _0xd1ceb6,
      _0x37013a
    ) => {
      const _0x37dd16 = _0x17dd9c;
      for (let _0x5b6d6b = 0x0; _0x5b6d6b < _0xd1ceb6; _0x5b6d6b++) {
        const _0x2d34dc = (_0x5b6d6b / _0xd1ceb6) * Math["PI"] * 0x2,
          _0x587053 = Math[_0x37dd16(0xe4)](_0x2d34dc) * _0x37013a,
          _0x587515 = Math[_0x37dd16(0x110)](_0x2d34dc) * _0x37013a,
          _0xd4d845 = new _0x1fb42a[_0x37dd16(0xee)](
            _0x303af8,
            _0x57a217,
            _0x280cd2,
            _0x3a7d7b
          );
        _0xd4d845["position"]["set"](_0x587053, 0x1, _0x587515),
          (_0xd4d845[_0x37dd16(0xd6)] = !![]),
          _0xaaa0b9[_0x37dd16(0x11a)](_0xd4d845);
      }
    },
    updateEnvironment = () => {
      const _0x21705e = _0x17dd9c,
        _0x2361a4 = environments[_0x21705e(0x130)](
          (_0x2a1718) =>
            _0x2a1718[_0x21705e(0x112)] === initialState["environment"]
        )[0x0];
      getCubeMapTexture(_0x2361a4)[_0x21705e(0xce)](({ envMap: _0x5527d0 }) => {
        exrEnv = _0x5527d0;
      });
    },
    getCubeMapTexture = (_0x22374d) => {
      const _0x465014 = _0x17dd9c;
      console[_0x465014(0xe2)](_0x465014(0xf0), _0x22374d);
      const { id: _0x4bb1f8, path: _0x37186d } = _0x22374d;
      if (_0x4bb1f8 === _0x465014(0x8b))
        return Promise[_0x465014(0xc6)]({ envMap: neutralEnvironment });
      if (_0x4bb1f8 === "") return Promise[_0x465014(0xc6)]({ envMap: null });
      return new Promise((_0x1ff8a0, _0x2275dd) => {
        new EXRLoader()["load"](
          _0x37186d,
          (_0x2e39c3) => {
            const _0x110f43 = _0x165e,
              _0x56acb5 =
                pmremGenerator[_0x110f43(0x86)](_0x2e39c3)[_0x110f43(0x119)];
            pmremGenerator[_0x110f43(0xdb)](),
              console["log"](_0x110f43(0xe1), _0x56acb5),
              _0x1ff8a0({ envMap: _0x56acb5 });
          },
          undefined,
          _0x2275dd
        );
      });
    },
    getDetailModel = (_0x3d0eeb) => {
      const _0x5ed34a = _0x17dd9c;
      console["log"](_0x5ed34a(0xc9)),
        _0x3d0eeb["preventDefault"](),
        (mouse["x"] =
          (_0x3d0eeb[_0x5ed34a(0x101)] / window[_0x5ed34a(0x109)]) * 0x2 - 0x1),
        (mouse["y"] =
          -(_0x3d0eeb[_0x5ed34a(0x9b)] / window[_0x5ed34a(0x84)]) * 0x2 + 0x1),
        raycaster[_0x5ed34a(0x90)](mouse, camera);
      let _0x135265 = raycaster[_0x5ed34a(0x11c)](scene[_0x5ed34a(0xbe)], !![]);
      if (_0x135265[_0x5ed34a(0xc3)] > 0x0) {
        let _0x569216 = _0x135265[0x0][_0x5ed34a(0xbc)];
        console[_0x5ed34a(0xe2)](
          _0x5ed34a(0xb9),
          _0x135265[0x0][_0x5ed34a(0xa3)]
        ),
          console["log"](_0x5ed34a(0xeb), _0x569216);
      }
    },
    animate = () => {
      const _0x52e8b1 = _0x17dd9c;
      requestAnimationFrame(animate),
        controls[_0x52e8b1(0x114)](),
        TWEEN[_0x52e8b1(0x114)](),
        ssrParams[_0x52e8b1(0xca)]
          ? composer[_0x52e8b1(0xb1)]()
          : renderer[_0x52e8b1(0xb1)](scene, camera);
    };
  function onWindowResize() {
    const _0x1c3ecf = _0x17dd9c,
      _0x496816 = window[_0x1c3ecf(0x109)],
      _0x349113 = window[_0x1c3ecf(0x84)];
    camera[_0x1c3ecf(0xd3)](),
      renderer[_0x1c3ecf(0x113)](_0x496816, _0x349113),
      composer[_0x1c3ecf(0x113)](_0x496816, _0x349113),
      groundReflector[_0x1c3ecf(0xd7)]()[_0x1c3ecf(0x113)](
        _0x496816,
        _0x349113
      ),
      groundReflector["resolution"][_0x1c3ecf(0xfe)](_0x496816, _0x349113);
  }
  const onOverViewButton = () => {
    const _0x481b47 = _0x17dd9c;
    isGoMallMode = !isGoMallMode;
    if (isGoMallMode) {
      textButtonView = _0x481b47(0xea);
      let _0x214a01 = {
        x: camera[_0x481b47(0x133)]["x"],
        y: camera[_0x481b47(0x133)]["y"],
        z: camera[_0x481b47(0x133)]["z"],
      };
      new TWEEN[_0x481b47(0xb7)](_0x214a01)
        ["to"]({
          x: 0.33266818379163465,
          y: 0.4567208098842309,
          z: 0.009396602938231524,
        })
        [_0x481b47(0x115)](() => {
          const _0x18bd03 = _0x481b47;
          return (
            controls[_0x18bd03(0xad)][_0x18bd03(0xfe)](
              -0.18035187854860613,
              0.34989708000472913,
              0.014436166392607084
            ),
            camera[_0x18bd03(0x133)]["copy"](_0x214a01)
          );
        })
        [_0x481b47(0x118)]();
    } else {
      textButtonView = _0x481b47(0xe0);
      let _0x3a898e = {
        x: camera["position"]["x"],
        y: camera[_0x481b47(0x133)]["y"],
        z: camera["position"]["z"],
      };
      new TWEEN[_0x481b47(0xb7)](_0x3a898e)
        ["to"]({ x: 0x0, y: 0x3, z: -0x1 })
        [_0x481b47(0x115)](() => {
          const _0x3f2eab = _0x481b47;
          return (
            controls[_0x3f2eab(0xad)][_0x3f2eab(0xfe)](0x0, 0x0, 0x0),
            camera["position"][_0x3f2eab(0xf4)](_0x3a898e)
          );
        })
        [_0x481b47(0x118)]();
    }
  };
  onMount(() => {
    const _0x244045 = _0x17dd9c;
    init(),
      animate(),
      window["addEventListener"](_0x244045(0xfa), onWindowResize);
  });
</script>

<main>
  <div class="view-button">
    <button
      style="--focus-color: {isGoMallMode ? '#fb8281' : '#006db6'}; "
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
