<script>
  const _0x2a118b = _0x45d1;
  (function (_0x47ee0a, _0xeefa16) {
    const _0x383719 = _0x45d1,
      _0x512199 = _0x47ee0a();
    while (!![]) {
      try {
        const _0x3e8842 =
          parseInt(_0x383719(0xae)) / 0x1 +
          (parseInt(_0x383719(0xda)) / 0x2) *
            (-parseInt(_0x383719(0x104)) / 0x3) +
          (parseInt(_0x383719(0xe5)) / 0x4) *
            (parseInt(_0x383719(0x9d)) / 0x5) +
          (-parseInt(_0x383719(0xd9)) / 0x6) *
            (parseInt(_0x383719(0xb5)) / 0x7) +
          (parseInt(_0x383719(0xee)) / 0x8) *
            (parseInt(_0x383719(0xa4)) / 0x9) +
          -parseInt(_0x383719(0xff)) / 0xa +
          (-parseInt(_0x383719(0x98)) / 0xb) *
            (parseInt(_0x383719(0xa6)) / 0xc);
        if (_0x3e8842 === _0xeefa16) break;
        else _0x512199["push"](_0x512199["shift"]());
      } catch (_0x32b7fe) {
        _0x512199["push"](_0x512199["shift"]());
      }
    }
  })(_0x1e9e, 0xb1e54);
  import * as _0x4c04ec from "../build/three.module";
  import { onMount, tick } from "svelte";
  import { GLTFLoader } from "../js/GLTFLoader";
  import { OrbitControls } from "../js/OrbitControls";
  import { TWEEN } from "../js/tween.module.min.js";
  import { EXRLoader } from "../js/EXRLoader.js";
  function _0x1e9e() {
    const _0x4fd420 = [
      "toneMapping",
      "Normal",
      "near",
      "type",
      "MeshBasicMaterial",
      "envMap",
      "8pIqbsS",
      "Color_M00158",
      "value",
      "push",
      "PerspectiveCamera",
      "Color_M00169",
      "Color_M00381",
      "getRenderTarget",
      "WebGLRenderer",
      "neutral",
      "Color_M00135",
      "name",
      "physicallyCorrectLights",
      "bouncing",
      "OUTPUT",
      "environment",
      "map",
      "5599930GxCDEZ",
      "offsetHeight",
      "screenSpaceRadius",
      "radiusExponent",
      "top",
      "15NxvgVe",
      "LinearMipmapLinearFilter",
      "material",
      "Color_M00127",
      "Color_M00426",
      "camera\x20position:\x20",
      "updatePdMaterial",
      "length",
      "Depth",
      "getPixelRatio",
      "innerWidth",
      "depthPhi",
      "otherMeshes",
      "resolution",
      "Color_M00197",
      "camera",
      "resolve",
      "ACESFilmicToneMapping",
      "Beauty",
      "resize",
      "pano_u",
      "error",
      "Home\x20Mode",
      "normalPhi",
      "render",
      "CubeCamera",
      "opacity",
      "background",
      "step",
      "output",
      "dampingFactor",
      "texture",
      "width",
      "PCFShadowMap",
      "log",
      "./assets/models/van/van2.glb",
      "infiniteThick",
      "castShadow",
      "Color_M00176",
      "close",
      "hide",
      "pano_r",
      "Tween",
      "mapSize",
      "compileEquirectangularShader",
      "Color_M00210",
      "Color_M00185",
      "rings",
      "outputEncoding",
      "selects",
      "min",
      "AmbientLight",
      "domElement",
      "PMREMGenerator",
      "add",
      "fresnel",
      "scale",
      "setPixelRatio",
      "uniforms",
      "70026druixp",
      "innerHeight",
      "addEventListener",
      "bias",
      "thickness",
      "7188605AQFdqg",
      "onUpdate",
      "Color",
      "Color_M00136",
      "addPass",
      "pano_b",
      "set",
      "1833525fYMcOV",
      "Enable\x20SSR",
      "1092psbNlk",
      "BoxGeometry",
      "forEach",
      "target",
      "copy",
      "DirectionalLight",
      "toneMappingExposure",
      "controls\x20target:\x20",
      "1160661JjNErg",
      ".jpg",
      "change",
      "sRGBEncoding",
      "Color_M00149",
      "shadow",
      "filter",
      "7KsBDtC",
      "position",
      "Raycaster",
      "visible",
      "distanceExponent",
      "scene",
      "groundReflector",
      "Default_150150150004",
      "max",
      "addFolder",
      "Box3",
      "pano_f",
      "setClearColor",
      "environment:\x20",
      "autoRotate",
      "rotation",
      "Color_M00173",
      "shadowMap",
      "encoding",
      "RGBAFormat",
      "enableSSR",
      "updateGtaoMaterial",
      "envMap:\x20",
      "pano_l",
      "onChange",
      "Default",
      "enabled",
      "fromScene",
      "pano_d",
      "left",
      "samples",
      "Scene",
      "Forest",
      "then",
      "radius",
      "updateProjectionMatrix",
      "4344498xdqhaJ",
      "84026LoAFKq",
      "distanceAttenuation",
      "load",
      "fromEquirectangular",
      "height",
      "update",
      "Color_M00181",
      "maxDistance",
      "isMesh",
      "distanceFallOff",
      "receiveShadow",
      "4QKiRwV",
      "depthWrite",
      "setSize",
    ];
    _0x1e9e = function () {
      return _0x4fd420;
    };
    return _0x1e9e();
  }
  import { environments } from "@public/assets/environment/index.js";
  import { RoomEnvironment } from "../js/RoomEnvironment.js";
  import { sRGBEncoding } from "../build/three.module";
  import { EffectComposer } from "../js/post-processing/EffectComposer.js";
  function _0x45d1(_0x42068f, _0x1fdf38) {
    const _0x1e9e18 = _0x1e9e();
    return (
      (_0x45d1 = function (_0x45d172, _0x143339) {
        _0x45d172 = _0x45d172 - 0x92;
        let _0x48f81d = _0x1e9e18[_0x45d172];
        return _0x48f81d;
      }),
      _0x45d1(_0x42068f, _0x1fdf38)
    );
  }
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
  let initialState = { environment: _0x2a118b(0xd5), background: ![] },
    pmremCubeRenderTarget,
    internalEnvMap;
  const widthScreen = window[_0x2a118b(0x10e)],
    heightScreen = window["innerHeight"],
    SHADOW_MAP_WIDTH = 0x800,
    SHADOW_MAP_HEIGHT = 0x400,
    vanElement = [
      "Color_M00168",
      _0x2a118b(0xef),
      _0x2a118b(0xa0),
      _0x2a118b(0xe0),
      _0x2a118b(0x112),
      "Default_150150150008",
      _0x2a118b(0x131),
      _0x2a118b(0xc5),
      _0x2a118b(0x12a),
      _0x2a118b(0x107),
      _0x2a118b(0x108),
      _0x2a118b(0xbc),
      _0x2a118b(0xf3),
      "Color_M00170",
      _0x2a118b(0xb2),
      _0x2a118b(0xf8),
      "Color_M00426",
      _0x2a118b(0xf4),
    ];
  let mouse = new _0x4c04ec["Vector2"](),
    raycaster = new _0x4c04ec[_0x2a118b(0xb7)](),
    isGoMallMode = ![],
    textButtonView = "View\x20Mode";
  const init = () => {
      const _0x21c06c = _0x2a118b;
      let _0x2931ed = "src/assets/cube-screen/",
        _0x56fcb0 = _0x21c06c(0xaf),
        _0x2785f1 = [
          _0x2931ed + _0x21c06c(0x12d) + _0x56fcb0,
          _0x2931ed + _0x21c06c(0xcc) + _0x56fcb0,
          _0x2931ed + _0x21c06c(0x118) + _0x56fcb0,
          _0x2931ed + _0x21c06c(0xd1) + _0x56fcb0,
          _0x2931ed + _0x21c06c(0xc0) + _0x56fcb0,
          _0x2931ed + _0x21c06c(0xa2) + _0x56fcb0,
        ];
      (camera = new _0x4c04ec[_0x21c06c(0xf2)](
        0x4b,
        widthScreen / heightScreen,
        0.1,
        0x64
      )),
        camera["position"][_0x21c06c(0xa3)](0x0, 0x3, -0x1),
        (scene = new _0x4c04ec[_0x21c06c(0xd4)]()),
        (scene[_0x21c06c(0x11f)] = new _0x4c04ec[_0x21c06c(0x9f)](0xcccccc)),
        (clock = new _0x4c04ec["Clock"]()),
        scene[_0x21c06c(0x93)](camera);
      const _0x280f6d = new _0x4c04ec[_0x21c06c(0x137)](0xffffff, 0.3);
      (_0x280f6d[_0x21c06c(0xf9)] = "ambient_light"),
        scene[_0x21c06c(0x93)](_0x280f6d);
      const _0x5380be = new _0x4c04ec[_0x21c06c(0xab)](
        0xffffff,
        0.8 * Math["PI"]
      );
      (_0x5380be[_0x21c06c(0x129)] = !![]),
        (_0x5380be[_0x21c06c(0xb3)][_0x21c06c(0x113)][_0x21c06c(0x103)] =
          0x7d0),
        (_0x5380be["shadow"][_0x21c06c(0x113)]["bottom"] = -0x7d0),
        (_0x5380be[_0x21c06c(0xb3)][_0x21c06c(0x113)][_0x21c06c(0xd2)] =
          -0x7d0),
        (_0x5380be[_0x21c06c(0xb3)][_0x21c06c(0x113)]["right"] = 0x7d0),
        (_0x5380be[_0x21c06c(0xb3)]["camera"][_0x21c06c(0xea)] = 0x4b0),
        (_0x5380be["shadow"][_0x21c06c(0x113)]["far"] = 0x9c4),
        (_0x5380be[_0x21c06c(0xb3)][_0x21c06c(0x9b)] = 0.0001),
        (_0x5380be[_0x21c06c(0xb3)][_0x21c06c(0x12f)][_0x21c06c(0x124)] =
          SHADOW_MAP_WIDTH),
        (_0x5380be[_0x21c06c(0xb3)][_0x21c06c(0x12f)][_0x21c06c(0xde)] =
          SHADOW_MAP_HEIGHT),
        scene["add"](_0x5380be),
        (renderer = new _0x4c04ec[_0x21c06c(0xf6)]({
          canvas: canvas,
          antialias: !![],
        })),
        (renderer[_0x21c06c(0xfa)] = !![]),
        (renderer[_0x21c06c(0x134)] = sRGBEncoding),
        renderer[_0x21c06c(0xc1)](0xcccccc),
        renderer[_0x21c06c(0x96)](window["devicePixelRatio"]),
        renderer[_0x21c06c(0xe7)](widthScreen, heightScreen),
        (renderer[_0x21c06c(0xe8)] = _0x4c04ec[_0x21c06c(0x115)]),
        (renderer[_0x21c06c(0xac)] = Math["pow"](0x2, 0x0)),
        (renderer["shadowMap"]["enabled"] = !![]),
        (renderer[_0x21c06c(0xc6)][_0x21c06c(0xeb)] =
          _0x4c04ec[_0x21c06c(0x125)]),
        (cubeRenderTarget = new _0x4c04ec["WebGLCubeRenderTarget"](0x400, {
          format: _0x4c04ec[_0x21c06c(0xc8)],
          generateMipmaps: !![],
          minFilter: _0x4c04ec[_0x21c06c(0x105)],
          encoding: _0x4c04ec[_0x21c06c(0xb1)],
        })),
        (cubeCamera = new _0x4c04ec[_0x21c06c(0x11d)](
          0x1,
          0x2710,
          cubeRenderTarget
        )),
        cubeCamera[_0x21c06c(0x95)][_0x21c06c(0xa3)](0.1, 0.1, 0.1),
        cubeCamera[_0x21c06c(0xb6)][_0x21c06c(0xa3)](-0.3, 0.65, 0x0);
      const _0x2f13aa = new _0x4c04ec[_0x21c06c(0xa7)](0x1, 0x1, 0x1),
        _0x19471f = new _0x4c04ec[_0x21c06c(0xec)]({ color: 0xff00 }),
        _0x40a7a4 = new _0x4c04ec["Mesh"](_0x2f13aa, _0x19471f);
      _0x40a7a4[_0x21c06c(0xb6)][_0x21c06c(0xa3)](-0.3, 0.65, 0x0);
      let _0x327bec = new _0x4c04ec["PlaneGeometry"](0x19, 0x19);
      (groundReflector = new ReflectorForSSRPass(_0x327bec, {
        clipBias: 0.0003,
        textureWidth: window[_0x21c06c(0x10e)],
        textureHeight: window[_0x21c06c(0x99)],
        color: 0x888888,
        useDepthTexture: !![],
      })),
        (groundReflector[_0x21c06c(0x106)][_0x21c06c(0xe6)] = ![]),
        (groundReflector[_0x21c06c(0xc4)]["x"] = -Math["PI"] / 0x2),
        (groundReflector[_0x21c06c(0xb8)] = ![]),
        cubeCamera["update"](renderer, scene),
        (pmremGenerator = new _0x4c04ec[_0x21c06c(0x92)](renderer)),
        pmremGenerator[_0x21c06c(0x130)](),
        (pmremCubeRenderTarget = pmremGenerator[_0x21c06c(0xdd)](
          cubeRenderTarget[_0x21c06c(0x123)]
        )),
        (internalEnvMap = pmremCubeRenderTarget?.["texture"]),
        (neutralEnvironment = pmremGenerator[_0x21c06c(0xd0)](
          new RoomEnvironment()
        )[_0x21c06c(0x123)]),
        (controls = new OrbitControls(camera, renderer[_0x21c06c(0x138)])),
        (controls[_0x21c06c(0xcf)] = !![]),
        (controls["enableDamping"] = !![]),
        (controls[_0x21c06c(0x122)] = 0.5),
        (composer = new EffectComposer(renderer));
      const _0xd41b2a = new RenderPass(scene, camera);
      composer["addPass"](_0xd41b2a);
      const _0x557a54 = new GTAOPass(scene, camera, widthScreen, heightScreen);
      (_0x557a54[_0x21c06c(0x121)] =
        GTAOPass[_0x21c06c(0xfc)][_0x21c06c(0xce)]),
        (ssrPass = new SSRPass({
          renderer: renderer,
          scene: scene,
          camera: camera,
          width: widthScreen,
          height: heightScreen,
          groundReflector: ssrParams[_0x21c06c(0xbb)] ? groundReflector : null,
          selects: ssrParams["groundReflector"] ? selects : null,
        })),
        composer["addPass"](ssrPass),
        composer[_0x21c06c(0xa1)](_0x557a54);
      const _0x135c8c = new ShaderPass(FXAAShader),
        _0x591492 = renderer[_0x21c06c(0x10d)]();
      (_0x135c8c[_0x21c06c(0x106)][_0x21c06c(0x97)][_0x21c06c(0x111)][
        _0x21c06c(0xf0)
      ]["x"] = 0x1 / (canvas["offsetWidth"] * _0x591492)),
        (_0x135c8c[_0x21c06c(0x106)][_0x21c06c(0x97)][_0x21c06c(0x111)][
          _0x21c06c(0xf0)
        ]["y"] = 0x1 / (canvas[_0x21c06c(0x100)] * _0x591492));
      const _0x3f8774 = new ShaderPass(GammaCorrectionShader);
      composer["addPass"](_0x3f8774);
      const _0x238c13 = new OutputPass();
      composer[_0x21c06c(0xa1)](_0x238c13),
        composer["addPass"](_0x135c8c),
        (loader = new GLTFLoader()),
        loader["load"](
          _0x21c06c(0x127),
          function (_0x46d9a4) {
            const _0x3d4ccf = _0x21c06c;
            (van = _0x46d9a4[_0x3d4ccf(0xba)]),
              van[_0x3d4ccf(0x95)][_0x3d4ccf(0xa3)](0xa, 0xa, 0xa),
              scene["add"](van),
              _0x46d9a4[_0x3d4ccf(0xba)]["traverse"](function (_0x46253b) {
                const _0x49afe7 = _0x3d4ccf;
                if (_0x46253b[_0x49afe7(0xe2)]) {
                  (_0x46253b[_0x49afe7(0x129)] = !![]),
                    (_0x46253b[_0x49afe7(0xe4)] = !![]);
                  for (
                    let _0x40f568 = 0x0;
                    _0x40f568 < vanElement[_0x49afe7(0x10b)];
                    _0x40f568++
                  ) {
                    if (_0x46253b["name"] == vanElement[_0x40f568]) {
                      (_0x46253b["material"]["envMap"] = exrEnv),
                        selects[_0x49afe7(0xf1)](_0x46253b);
                      break;
                    } else {
                      if (_0x46253b["name"] != _0x49afe7(0x132)) {
                        selects[_0x49afe7(0xf1)](_0x46253b),
                          otherMeshes[_0x49afe7(0xf1)](_0x46253b),
                          (_0x46253b[_0x49afe7(0x106)][_0x49afe7(0xed)] =
                            cubeRenderTarget["texture"]);
                        if (_0x46253b[_0x49afe7(0x106)][_0x49afe7(0xfe)])
                          _0x46253b[_0x49afe7(0x106)][_0x49afe7(0xfe)][
                            "encoding"
                          ] = sRGBEncoding;
                        if (_0x46253b["material"]["emissiveMap"])
                          _0x46253b[_0x49afe7(0x106)]["emissiveMap"][
                            _0x49afe7(0xc7)
                          ] = sRGBEncoding;
                        if (
                          _0x46253b[_0x49afe7(0x106)][_0x49afe7(0xfe)] ||
                          _0x46253b[_0x49afe7(0x106)]["emissiveMap"]
                        )
                          _0x46253b[_0x49afe7(0x106)]["needsUpdate"] = !![];
                      }
                    }
                  }
                  (_0x46253b[_0x49afe7(0xf9)] == _0x49afe7(0xf8) ||
                    _0x46253b[_0x49afe7(0xf9)] == _0x49afe7(0x108)) &&
                    (_0x46253b[_0x49afe7(0xb8)] = ![]);
                  const _0x56c943 = new _0x4c04ec[_0x49afe7(0xbf)]()[
                    "setFromObject"
                  ](scene);
                  return _0x557a54["setSceneClipBox"](_0x56c943), _0x46253b;
                }
              }),
              cubeCamera[_0x3d4ccf(0xdf)](renderer, scene);
          },
          undefined,
          function (_0xa606f2) {
            const _0x2e888c = _0x21c06c;
            console[_0x2e888c(0x119)](_0xa606f2);
          }
        ),
        updateEnvironment(),
        cubeCamera[_0x21c06c(0xdf)](renderer, scene);
      const _0x586303 = new GUI();
      _0x586303[_0x21c06c(0x93)](_0x557a54, _0x21c06c(0x121), {
        Default: GTAOPass[_0x21c06c(0xfc)][_0x21c06c(0xce)],
        Diffuse: GTAOPass["OUTPUT"]["Diffuse"],
        "AO\x20Only": GTAOPass[_0x21c06c(0xfc)]["AO"],
        "AO\x20Only\x20+\x20Denoise": GTAOPass["OUTPUT"]["Denoise"],
        Depth: GTAOPass[_0x21c06c(0xfc)][_0x21c06c(0x10c)],
        Normal: GTAOPass[_0x21c06c(0xfc)][_0x21c06c(0xe9)],
      })[_0x21c06c(0xcd)](function (_0x54e03d) {
        const _0x561c10 = _0x21c06c;
        _0x557a54[_0x561c10(0x121)] = _0x54e03d;
      });
      const _0x339468 = {
          radius: 0.2,
          distanceExponent: 1.85,
          thickness: 0x1,
          scale: 1.5,
          samples: 0x20,
          distanceFallOff: 0x1,
          screenSpaceRadius: ![],
        },
        _0x35cd0d = {
          lumaPhi: 0xa,
          depthPhi: 0x2,
          normalPhi: 0x3,
          radius: 0.5,
          radiusExponent: 0x1,
          rings: 0x2,
          samples: 0x20,
        };
      _0x557a54["updateGtaoMaterial"](_0x339468),
        _0x557a54[_0x21c06c(0x10a)](_0x35cd0d),
        _0x586303[_0x21c06c(0x93)](_0x557a54, "blendIntensity")
          [_0x21c06c(0x136)](0x0)
          [_0x21c06c(0xbd)](0x1)
          [_0x21c06c(0x120)](0.01),
        _0x586303[_0x21c06c(0x93)](_0x339468, _0x21c06c(0xd7))
          [_0x21c06c(0x136)](0.01)
          ["max"](0x1)
          [_0x21c06c(0x120)](0.01)
          [_0x21c06c(0xcd)](() => _0x557a54[_0x21c06c(0xca)](_0x339468)),
        _0x586303[_0x21c06c(0x93)](_0x339468, _0x21c06c(0xb9))
          [_0x21c06c(0x136)](0x1)
          [_0x21c06c(0xbd)](0x4)
          [_0x21c06c(0x120)](0.01)
          [_0x21c06c(0xcd)](() => _0x557a54[_0x21c06c(0xca)](_0x339468)),
        _0x586303[_0x21c06c(0x93)](_0x339468, _0x21c06c(0x9c))
          [_0x21c06c(0x136)](0.01)
          [_0x21c06c(0xbd)](0xa)
          ["step"](0.01)
          [_0x21c06c(0xcd)](() => _0x557a54["updateGtaoMaterial"](_0x339468)),
        _0x586303[_0x21c06c(0x93)](_0x339468, _0x21c06c(0xe3))
          [_0x21c06c(0x136)](0x0)
          [_0x21c06c(0xbd)](0x1)
          [_0x21c06c(0x120)](0.01)
          [_0x21c06c(0xcd)](() => _0x557a54[_0x21c06c(0xca)](_0x339468)),
        _0x586303[_0x21c06c(0x93)](_0x339468, _0x21c06c(0x95))
          ["min"](0.01)
          [_0x21c06c(0xbd)](0x2)
          ["step"](0.01)
          [_0x21c06c(0xcd)](() => _0x557a54["updateGtaoMaterial"](_0x339468)),
        _0x586303["add"](_0x339468, _0x21c06c(0xd3))
          [_0x21c06c(0x136)](0x2)
          [_0x21c06c(0xbd)](0x20)
          ["step"](0x1)
          [_0x21c06c(0xcd)](() => _0x557a54["updateGtaoMaterial"](_0x339468)),
        _0x586303[_0x21c06c(0x93)](_0x339468, _0x21c06c(0x101))[
          _0x21c06c(0xcd)
        ](() => _0x557a54[_0x21c06c(0xca)](_0x339468)),
        _0x586303[_0x21c06c(0x93)](_0x35cd0d, "lumaPhi")
          [_0x21c06c(0x136)](0x0)
          [_0x21c06c(0xbd)](0x14)
          [_0x21c06c(0x120)](0.01)
          [_0x21c06c(0xcd)](() => _0x557a54[_0x21c06c(0x10a)](_0x35cd0d)),
        _0x586303["add"](_0x35cd0d, _0x21c06c(0x10f))
          [_0x21c06c(0x136)](0.01)
          [_0x21c06c(0xbd)](0x14)
          [_0x21c06c(0x120)](0.01)
          [_0x21c06c(0xcd)](() => _0x557a54["updatePdMaterial"](_0x35cd0d)),
        _0x586303["add"](_0x35cd0d, _0x21c06c(0x11b))
          [_0x21c06c(0x136)](0.01)
          [_0x21c06c(0xbd)](0x14)
          ["step"](0.01)
          [_0x21c06c(0xcd)](() => _0x557a54[_0x21c06c(0x10a)](_0x35cd0d)),
        _0x586303["add"](_0x35cd0d, _0x21c06c(0xd7))
          [_0x21c06c(0x136)](0x0)
          [_0x21c06c(0xbd)](0x20)
          [_0x21c06c(0x120)](0x1)
          ["onChange"](() => _0x557a54[_0x21c06c(0x10a)](_0x35cd0d)),
        _0x586303[_0x21c06c(0x93)](_0x35cd0d, _0x21c06c(0x102))
          ["min"](0.1)
          [_0x21c06c(0xbd)](0x4)
          [_0x21c06c(0x120)](0.1)
          [_0x21c06c(0xcd)](() => _0x557a54[_0x21c06c(0x10a)](_0x35cd0d)),
        _0x586303[_0x21c06c(0x93)](_0x35cd0d, _0x21c06c(0x133))
          [_0x21c06c(0x136)](0x1)
          [_0x21c06c(0xbd)](0x10)
          ["step"](0.125)
          ["onChange"](() => _0x557a54[_0x21c06c(0x10a)](_0x35cd0d)),
        _0x586303["add"](_0x35cd0d, _0x21c06c(0xd3))
          [_0x21c06c(0x136)](0x2)
          [_0x21c06c(0xbd)](0x20)
          [_0x21c06c(0x120)](0x1)
          [_0x21c06c(0xcd)](() => _0x557a54[_0x21c06c(0x10a)](_0x35cd0d)),
        _0x586303[_0x21c06c(0x93)](ssrParams, "enableSSR")[_0x21c06c(0xf9)](
          _0x21c06c(0xa5)
        ),
        _0x586303[_0x21c06c(0x93)](ssrParams, _0x21c06c(0xbb))[_0x21c06c(0xcd)](
          () => {
            const _0x2aa6fd = _0x21c06c;
            ssrParams["groundReflector"]
              ? ((ssrPass[_0x2aa6fd(0xbb)] = groundReflector),
                (ssrPass[_0x2aa6fd(0x135)] = selects))
              : ((ssrPass[_0x2aa6fd(0xbb)] = null),
                (ssrPass[_0x2aa6fd(0x135)] = null));
          }
        ),
        (ssrPass["thickness"] = 0.018),
        _0x586303["add"](ssrPass, _0x21c06c(0x9c))
          ["min"](0x0)
          [_0x21c06c(0xbd)](0.1)
          [_0x21c06c(0x120)](0.0001),
        (ssrPass[_0x21c06c(0x128)] = ![]),
        _0x586303[_0x21c06c(0x93)](ssrPass, _0x21c06c(0x128)),
        _0x586303["add"](ssrParams, _0x21c06c(0xc3))[_0x21c06c(0xcd)](() => {
          const _0x31879a = _0x21c06c;
          controls[_0x31879a(0xcf)] = !ssrParams["autoRotate"];
        });
      const _0x3e355f = _0x586303[_0x21c06c(0xbe)]("more\x20settings");
      _0x3e355f["add"](ssrPass, _0x21c06c(0x94))[_0x21c06c(0xcd)](() => {
        const _0x260b9c = _0x21c06c;
        groundReflector[_0x260b9c(0x94)] = ssrPass["fresnel"];
      }),
        _0x3e355f[_0x21c06c(0x93)](ssrPass, "distanceAttenuation")[
          _0x21c06c(0xcd)
        ](() => {
          const _0x3ea222 = _0x21c06c;
          groundReflector["distanceAttenuation"] = ssrPass[_0x3ea222(0xdb)];
        }),
        (ssrPass[_0x21c06c(0xe1)] = 0.3),
        (groundReflector["maxDistance"] = ssrPass["maxDistance"]),
        _0x3e355f[_0x21c06c(0x93)](ssrPass, _0x21c06c(0xe1))
          [_0x21c06c(0x136)](0x0)
          [_0x21c06c(0xbd)](0.5)
          ["step"](0.001)
          [_0x21c06c(0xcd)](() => {
            const _0x489081 = _0x21c06c;
            groundReflector[_0x489081(0xe1)] = ssrPass[_0x489081(0xe1)];
          }),
        _0x3e355f["add"](ssrParams, "otherMeshes")[_0x21c06c(0xcd)](() => {
          const _0x39b0d2 = _0x21c06c;
          ssrParams[_0x39b0d2(0x110)]
            ? otherMeshes[_0x39b0d2(0xa8)](
                (_0x1e6700) => (_0x1e6700[_0x39b0d2(0xb8)] = !![])
              )
            : otherMeshes[_0x39b0d2(0xa8)](
                (_0x3427a7) => (_0x3427a7[_0x39b0d2(0xb8)] = ![])
              );
        }),
        _0x3e355f[_0x21c06c(0x93)](ssrPass, _0x21c06c(0xfb)),
        _0x3e355f[_0x21c06c(0x93)](ssrPass, "output", {
          Default: SSRPass[_0x21c06c(0xfc)][_0x21c06c(0xce)],
          "SSR\x20Only": SSRPass[_0x21c06c(0xfc)]["SSR"],
          Beauty: SSRPass[_0x21c06c(0xfc)][_0x21c06c(0x116)],
          Depth: SSRPass[_0x21c06c(0xfc)][_0x21c06c(0x10c)],
          Normal: SSRPass[_0x21c06c(0xfc)]["Normal"],
          Metalness: SSRPass[_0x21c06c(0xfc)]["Metalness"],
        })[_0x21c06c(0xcd)](function (_0x3e995d) {
          const _0x554d3b = _0x21c06c;
          ssrPass[_0x554d3b(0x121)] = _0x3e995d;
        }),
        (ssrPass[_0x21c06c(0x11e)] = 0.5),
        (groundReflector[_0x21c06c(0x11e)] = ssrPass[_0x21c06c(0x11e)]),
        _0x3e355f[_0x21c06c(0x93)](ssrPass, _0x21c06c(0x11e))
          ["min"](0x0)
          [_0x21c06c(0xbd)](0x1)
          [_0x21c06c(0xcd)](() => {
            const _0x9e8422 = _0x21c06c;
            groundReflector["opacity"] = ssrPass[_0x9e8422(0x11e)];
          }),
        _0x3e355f["add"](ssrPass, "blur"),
        _0x586303[_0x21c06c(0x12b)](),
        _0x586303[_0x21c06c(0x12c)](),
        controls[_0x21c06c(0x9a)](_0x21c06c(0xb0), () => {
          const _0x4b7766 = _0x21c06c;
          console[_0x4b7766(0x126)](_0x4b7766(0x109), camera[_0x4b7766(0xb6)]),
            console[_0x4b7766(0x126)](_0x4b7766(0xad), controls["target"]);
        });
    },
    updateEnvironment = () => {
      const _0x1a7e15 = _0x2a118b,
        _0xc58e8f = environments[_0x1a7e15(0xb4)](
          (_0x214bc4) =>
            _0x214bc4[_0x1a7e15(0xf9)] === initialState[_0x1a7e15(0xfd)]
        )[0x0];
      console[_0x1a7e15(0x126)](_0x1a7e15(0xc2), _0xc58e8f),
        getCubeMapTexture(_0xc58e8f)[_0x1a7e15(0xd6)](
          ({ envMap: _0x4dc892 }) => {
            exrEnv = _0x4dc892;
          }
        );
    },
    getCubeMapTexture = (_0x297bf9) => {
      const _0x3dffab = _0x2a118b,
        { id: _0x32b74d, path: _0x435a24 } = _0x297bf9;
      if (_0x32b74d === _0x3dffab(0xf7))
        return Promise[_0x3dffab(0x114)]({ envMap: neutralEnvironment });
      if (_0x32b74d === "") return Promise[_0x3dffab(0x114)]({ envMap: null });
      return new Promise((_0x3a6675, _0x2d1e10) => {
        const _0x4b4470 = _0x3dffab;
        new EXRLoader()[_0x4b4470(0xdc)](
          _0x435a24,
          (_0x392478) => {
            const _0x1b611e = _0x4b4470,
              _0x20cd22 =
                pmremGenerator[_0x1b611e(0xdd)](_0x392478)[_0x1b611e(0x123)];
            pmremGenerator["dispose"](),
              console[_0x1b611e(0x126)](_0x1b611e(0xcb), _0x20cd22),
              _0x3a6675({ envMap: _0x20cd22 });
          },
          undefined,
          _0x2d1e10
        );
      });
    },
    animate = () => {
      const _0x3c38d6 = _0x2a118b;
      requestAnimationFrame(animate),
        controls["update"](),
        TWEEN["update"](),
        ssrParams[_0x3c38d6(0xc9)]
          ? composer["render"]()
          : renderer[_0x3c38d6(0x11c)](scene, camera);
    };
  function onWindowResize() {
    const _0x206b50 = _0x2a118b,
      _0x2e7fc9 = window["innerWidth"],
      _0x25a42a = window[_0x206b50(0x99)];
    camera[_0x206b50(0xd8)](),
      renderer[_0x206b50(0xe7)](_0x2e7fc9, _0x25a42a),
      composer[_0x206b50(0xe7)](_0x2e7fc9, _0x25a42a),
      groundReflector[_0x206b50(0xf5)]()[_0x206b50(0xe7)](_0x2e7fc9, _0x25a42a),
      groundReflector["resolution"]["set"](_0x2e7fc9, _0x25a42a);
  }
  const onOverViewButton = () => {
    const _0x5f0668 = _0x2a118b;
    isGoMallMode = !isGoMallMode;
    if (isGoMallMode) {
      textButtonView = _0x5f0668(0x11a);
      let _0x5c1b98 = {
        x: camera[_0x5f0668(0xb6)]["x"],
        y: camera[_0x5f0668(0xb6)]["y"],
        z: camera[_0x5f0668(0xb6)]["z"],
      };
      new TWEEN[_0x5f0668(0x12e)](_0x5c1b98)
        ["to"]({
          x: 0.33266818379163465,
          y: 0.4567208098842309,
          z: 0.009396602938231524,
        })
        ["onUpdate"](() => {
          const _0x88e7e4 = _0x5f0668;
          return (
            controls[_0x88e7e4(0xa9)][_0x88e7e4(0xa3)](
              -0.18035187854860613,
              0.34989708000472913,
              0.014436166392607084
            ),
            camera[_0x88e7e4(0xb6)]["copy"](_0x5c1b98)
          );
        })
        ["start"]();
    } else {
      textButtonView = "View\x20Mode";
      let _0x27feca = {
        x: camera["position"]["x"],
        y: camera[_0x5f0668(0xb6)]["y"],
        z: camera[_0x5f0668(0xb6)]["z"],
      };
      new TWEEN["Tween"](_0x27feca)
        ["to"]({ x: 0x0, y: 0x3, z: -0x1 })
        [_0x5f0668(0x9e)](() => {
          const _0x2e1823 = _0x5f0668;
          return (
            controls["target"][_0x2e1823(0xa3)](0x0, 0x0, 0x0),
            camera[_0x2e1823(0xb6)][_0x2e1823(0xaa)](_0x27feca)
          );
        })
        ["start"]();
    }
  };
  onMount(() => {
    const _0x43d1ff = _0x2a118b;
    init(),
      animate(),
      window[_0x43d1ff(0x9a)](_0x43d1ff(0x117), onWindowResize);
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
