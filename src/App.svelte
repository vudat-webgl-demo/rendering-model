<script>
  const _0x4773e2 = _0x4b66;
  (function (_0xf92b7c, _0x1152ab) {
    const _0x2c4f44 = _0x4b66,
      _0xc10343 = _0xf92b7c();
    while (!![]) {
      try {
        const _0x2d6fb7 =
          (-parseInt(_0x2c4f44(0x1ce)) / 0x1) *
            (-parseInt(_0x2c4f44(0x1ed)) / 0x2) +
          -parseInt(_0x2c4f44(0x1a0)) / 0x3 +
          -parseInt(_0x2c4f44(0x172)) / 0x4 +
          (-parseInt(_0x2c4f44(0x1c2)) / 0x5) *
            (parseInt(_0x2c4f44(0x19b)) / 0x6) +
          (-parseInt(_0x2c4f44(0x1d9)) / 0x7) *
            (-parseInt(_0x2c4f44(0x1ee)) / 0x8) +
          (parseInt(_0x2c4f44(0x1ec)) / 0x9) *
            (-parseInt(_0x2c4f44(0x1b3)) / 0xa) +
          parseInt(_0x2c4f44(0x1cb)) / 0xb;
        if (_0x2d6fb7 === _0x1152ab) break;
        else _0xc10343["push"](_0xc10343["shift"]());
      } catch (_0x26f855) {
        _0xc10343["push"](_0xc10343["shift"]());
      }
    }
  })(_0xd880, 0x719e6);
  import * as _0x87ac58 from "../build/three.module";
  import { onMount, tick } from "svelte";
  import { GLTFLoader } from "../js/GLTFLoader";
  import { OrbitControls } from "../js/OrbitControls";
  function _0xd880() {
    const _0x351633 = [
      "render",
      "ambient_light",
      "pano_u",
      "opacity",
      "forEach",
      "scene",
      "fresnel",
      "emissiveMap",
      "BoxGeometry",
      "Denoise",
      "enabled",
      "type",
      "envMap:\x20",
      "target",
      "Color_M00210",
      "Color_M00149",
      "dispose",
      "Color_M00170",
      "offsetHeight",
      "getPixelRatio",
      "Color_M00168",
      "infiniteThick",
      "Normal",
      "camera",
      "OUTPUT",
      "distanceExponent",
      "View\x20Mode",
      "copy",
      "Color",
      "width",
      "2647494RWHpkV",
      "updateGtaoMaterial",
      "resolve",
      "getRenderTarget",
      "Box3",
      "1323243fgXTKV",
      "far",
      "length",
      "radius",
      "addEventListener",
      "hide",
      "push",
      "distanceFallOff",
      "otherMeshes",
      "selects",
      "Color_M00381",
      "texture",
      "error",
      "material",
      "update",
      "Color_M00136",
      "bottom",
      "position",
      "lumaPhi",
      "1066930ChugKU",
      "autoRotate",
      "Tween",
      "depthPhi",
      "change",
      "Color_M00135",
      "Color_M00181",
      "load",
      "Beauty",
      "uniforms",
      "domElement",
      "Default_150150150004",
      "height",
      "castShadow",
      "groundReflector",
      "5OaliUN",
      "innerWidth",
      "setPixelRatio",
      "Diffuse",
      "DirectionalLight",
      "Home\x20Mode",
      "log",
      "resolution",
      "map",
      "479831gBjCqI",
      "Mesh",
      "blur",
      "7ZxHpPB",
      "envMap",
      "normalPhi",
      "pano_d",
      "setFromObject",
      "shadow",
      "Default_150150150008",
      "samples",
      "receiveShadow",
      "background",
      "setSize",
      "7rPArLB",
      "CubeCamera",
      "near",
      "WebGLCubeRenderTarget",
      "addFolder",
      "blendIntensity",
      "Vector2",
      "fromEquirectangular",
      "devicePixelRatio",
      "step",
      "innerHeight",
      "visible",
      "max",
      "bias",
      "PerspectiveCamera",
      "Color_M00158",
      "isMesh",
      "onChange",
      "screenSpaceRadius",
      "9RnGvlG",
      "246510vhwypq",
      "7189992iHqCfn",
      "RGBAFormat",
      "camera\x20position:\x20",
      "top",
      "Color_M00426",
      "pano_r",
      ".jpg",
      "addPass",
      "mapSize",
      "setClearColor",
      "enableDamping",
      "Enable\x20SSR",
      "ACESFilmicToneMapping",
      "fromScene",
      "Forest",
      "toneMappingExposure",
      "bouncing",
      "Default",
      "dampingFactor",
      "offsetWidth",
      "Metalness",
      "Depth",
      "PlaneGeometry",
      "set",
      "needsUpdate",
      "physicallyCorrectLights",
      "scale",
      "left",
      "toneMapping",
      "distanceAttenuation",
      "name",
      "value",
      "add",
      "Color_M00185",
      "Clock",
      "close",
      "WebGLRenderer",
      "maxDistance",
      "output",
      "encoding",
      "updatePdMaterial",
      "1403000HjTqZl",
      "onUpdate",
      "LinearMipmapLinearFilter",
      "thickness",
      "resize",
      "pano_b",
      "start",
      "filter",
      "PMREMGenerator",
      "controls\x20target:\x20",
      "min",
    ];
    _0xd880 = function () {
      return _0x351633;
    };
    return _0xd880();
  }
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
  function _0x4b66(_0x48d5e4, _0x4f7809) {
    const _0xd880a6 = _0xd880();
    return (
      (_0x4b66 = function (_0x4b6667, _0x1f3edd) {
        _0x4b6667 = _0x4b6667 - 0x14a;
        let _0xfa78bb = _0xd880a6[_0x4b6667];
        return _0xfa78bb;
      }),
      _0x4b66(_0x48d5e4, _0x4f7809)
    );
  }
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
  let initialState = { environment: _0x4773e2(0x157), background: ![] },
    pmremCubeRenderTarget,
    internalEnvMap;
  const widthScreen = window[_0x4773e2(0x1c3)],
    heightScreen = window[_0x4773e2(0x1e3)],
    SHADOW_MAP_WIDTH = 0x800,
    SHADOW_MAP_HEIGHT = 0x400,
    vanElement = [
      _0x4773e2(0x191),
      _0x4773e2(0x1e8),
      _0x4773e2(0x1af),
      _0x4773e2(0x1b9),
      "Color_M00197",
      _0x4773e2(0x1d4),
      _0x4773e2(0x18b),
      "Color_M00173",
      "Color_M00176",
      "Color_M00127",
      _0x4773e2(0x14d),
      _0x4773e2(0x1be),
      "Color_M00169",
      _0x4773e2(0x18e),
      _0x4773e2(0x18c),
      _0x4773e2(0x1b8),
      "Color_M00426",
      _0x4773e2(0x1aa),
    ];
  let mouse = new _0x87ac58[_0x4773e2(0x1df)](),
    raycaster = new _0x87ac58["Raycaster"](),
    isGoMallMode = ![],
    textButtonView = _0x4773e2(0x197);
  const init = () => {
      const _0x24c8dc = _0x4773e2;
      let _0x20a109 = "src/assets/cube-screen/",
        _0x4eedbc = _0x24c8dc(0x14f),
        _0x274f0a = [
          _0x20a109 + _0x24c8dc(0x14e) + _0x4eedbc,
          _0x20a109 + "pano_l" + _0x4eedbc,
          _0x20a109 + _0x24c8dc(0x17f) + _0x4eedbc,
          _0x20a109 + _0x24c8dc(0x1d1) + _0x4eedbc,
          _0x20a109 + "pano_f" + _0x4eedbc,
          _0x20a109 + _0x24c8dc(0x177) + _0x4eedbc,
        ];
      (camera = new _0x87ac58[_0x24c8dc(0x1e7)](
        0x4b,
        widthScreen / heightScreen,
        0.1,
        0x64
      )),
        camera["position"][_0x24c8dc(0x160)](0x0, 0x3, -0x1),
        (scene = new _0x87ac58["Scene"]()),
        (scene[_0x24c8dc(0x1d7)] = new _0x87ac58[_0x24c8dc(0x199)](0xcccccc)),
        (clock = new _0x87ac58[_0x24c8dc(0x16b)]()),
        scene[_0x24c8dc(0x169)](camera);
      const _0x47d47f = new _0x87ac58["AmbientLight"](0xffffff, 0.3);
      (_0x47d47f[_0x24c8dc(0x167)] = _0x24c8dc(0x17e)),
        scene[_0x24c8dc(0x169)](_0x47d47f);
      const _0x3fdb9e = new _0x87ac58[_0x24c8dc(0x1c6)](
        0xffffff,
        0.8 * Math["PI"]
      );
      (_0x3fdb9e[_0x24c8dc(0x1c0)] = !![]),
        (_0x3fdb9e[_0x24c8dc(0x1d3)][_0x24c8dc(0x194)][_0x24c8dc(0x14c)] =
          0x7d0),
        (_0x3fdb9e[_0x24c8dc(0x1d3)]["camera"][_0x24c8dc(0x1b0)] = -0x7d0),
        (_0x3fdb9e[_0x24c8dc(0x1d3)]["camera"][_0x24c8dc(0x164)] = -0x7d0),
        (_0x3fdb9e[_0x24c8dc(0x1d3)][_0x24c8dc(0x194)]["right"] = 0x7d0),
        (_0x3fdb9e["shadow"][_0x24c8dc(0x194)][_0x24c8dc(0x1db)] = 0x4b0),
        (_0x3fdb9e[_0x24c8dc(0x1d3)]["camera"][_0x24c8dc(0x1a1)] = 0x9c4),
        (_0x3fdb9e[_0x24c8dc(0x1d3)][_0x24c8dc(0x1e6)] = 0.0001),
        (_0x3fdb9e["shadow"][_0x24c8dc(0x151)][_0x24c8dc(0x19a)] =
          SHADOW_MAP_WIDTH),
        (_0x3fdb9e[_0x24c8dc(0x1d3)][_0x24c8dc(0x151)][_0x24c8dc(0x1bf)] =
          SHADOW_MAP_HEIGHT),
        scene[_0x24c8dc(0x169)](_0x3fdb9e),
        (renderer = new _0x87ac58[_0x24c8dc(0x16d)]({
          canvas: canvas,
          antialias: !![],
        })),
        (renderer[_0x24c8dc(0x162)] = !![]),
        (renderer["outputEncoding"] = sRGBEncoding),
        renderer[_0x24c8dc(0x152)](0xcccccc),
        renderer[_0x24c8dc(0x1c4)](window[_0x24c8dc(0x1e1)]),
        renderer[_0x24c8dc(0x1d8)](widthScreen, heightScreen),
        (renderer[_0x24c8dc(0x165)] = _0x87ac58[_0x24c8dc(0x155)]),
        (renderer[_0x24c8dc(0x158)] = Math["pow"](0x2, 0x0)),
        (renderer["shadowMap"][_0x24c8dc(0x187)] = !![]),
        (renderer["shadowMap"][_0x24c8dc(0x188)] = _0x87ac58["PCFShadowMap"]),
        (cubeRenderTarget = new _0x87ac58[_0x24c8dc(0x1dc)](0x400, {
          format: _0x87ac58[_0x24c8dc(0x14a)],
          generateMipmaps: !![],
          minFilter: _0x87ac58[_0x24c8dc(0x174)],
          encoding: _0x87ac58["sRGBEncoding"],
        })),
        (cubeCamera = new _0x87ac58[_0x24c8dc(0x1da)](
          0x1,
          0x2710,
          cubeRenderTarget
        )),
        cubeCamera["scale"][_0x24c8dc(0x160)](0.1, 0.1, 0.1),
        cubeCamera[_0x24c8dc(0x1b1)][_0x24c8dc(0x160)](-0.3, 0.65, 0x0);
      const _0x4cc00b = new _0x87ac58[_0x24c8dc(0x185)](0x1, 0x1, 0x1),
        _0x221e88 = new _0x87ac58["MeshBasicMaterial"]({ color: 0xff00 }),
        _0x17acfc = new _0x87ac58[_0x24c8dc(0x1cc)](_0x4cc00b, _0x221e88);
      _0x17acfc[_0x24c8dc(0x1b1)]["set"](-0.3, 0.65, 0x0);
      let _0x134445 = new _0x87ac58[_0x24c8dc(0x15f)](0x19, 0x19);
      (groundReflector = new ReflectorForSSRPass(_0x134445, {
        clipBias: 0.0003,
        textureWidth: window[_0x24c8dc(0x1c3)],
        textureHeight: window[_0x24c8dc(0x1e3)],
        color: 0x888888,
        useDepthTexture: !![],
      })),
        (groundReflector[_0x24c8dc(0x1ad)]["depthWrite"] = ![]),
        (groundReflector["rotation"]["x"] = -Math["PI"] / 0x2),
        (groundReflector[_0x24c8dc(0x1e4)] = ![]),
        cubeCamera[_0x24c8dc(0x1ae)](renderer, scene),
        (pmremGenerator = new _0x87ac58[_0x24c8dc(0x17a)](renderer)),
        pmremGenerator["compileEquirectangularShader"](),
        (pmremCubeRenderTarget = pmremGenerator[_0x24c8dc(0x1e0)](
          cubeRenderTarget["texture"]
        )),
        (internalEnvMap = pmremCubeRenderTarget?.[_0x24c8dc(0x1ab)]),
        (neutralEnvironment = pmremGenerator[_0x24c8dc(0x156)](
          new RoomEnvironment()
        )[_0x24c8dc(0x1ab)]),
        (controls = new OrbitControls(camera, renderer[_0x24c8dc(0x1bd)])),
        (controls[_0x24c8dc(0x187)] = !![]),
        (controls[_0x24c8dc(0x153)] = !![]),
        (controls[_0x24c8dc(0x15b)] = 0.5),
        (composer = new EffectComposer(renderer));
      const _0x51b92c = new RenderPass(scene, camera);
      composer[_0x24c8dc(0x150)](_0x51b92c);
      const _0x2a4b3a = new GTAOPass(scene, camera, widthScreen, heightScreen);
      (_0x2a4b3a[_0x24c8dc(0x16f)] =
        GTAOPass[_0x24c8dc(0x195)][_0x24c8dc(0x15a)]),
        (ssrPass = new SSRPass({
          renderer: renderer,
          scene: scene,
          camera: camera,
          width: widthScreen,
          height: heightScreen,
          groundReflector: ssrParams[_0x24c8dc(0x1c1)] ? groundReflector : null,
          selects: ssrParams["groundReflector"] ? selects : null,
        })),
        composer[_0x24c8dc(0x150)](ssrPass),
        composer["addPass"](_0x2a4b3a);
      const _0x23522d = new ShaderPass(FXAAShader),
        _0x194789 = renderer[_0x24c8dc(0x190)]();
      (_0x23522d["material"][_0x24c8dc(0x1bc)]["resolution"][_0x24c8dc(0x168)][
        "x"
      ] = 0x1 / (canvas[_0x24c8dc(0x15c)] * _0x194789)),
        (_0x23522d[_0x24c8dc(0x1ad)][_0x24c8dc(0x1bc)][_0x24c8dc(0x1c9)][
          _0x24c8dc(0x168)
        ]["y"] = 0x1 / (canvas[_0x24c8dc(0x18f)] * _0x194789));
      const _0x3cf68f = new ShaderPass(GammaCorrectionShader);
      composer[_0x24c8dc(0x150)](_0x3cf68f);
      const _0x556999 = new OutputPass();
      composer[_0x24c8dc(0x150)](_0x556999),
        composer[_0x24c8dc(0x150)](_0x23522d),
        (loader = new GLTFLoader()),
        loader[_0x24c8dc(0x1ba)](
          "./assets/models/van/van2.glb",
          function (_0x11f8be) {
            const _0x2223ba = _0x24c8dc;
            (van = _0x11f8be["scene"]),
              van[_0x2223ba(0x163)][_0x2223ba(0x160)](0xa, 0xa, 0xa),
              scene["add"](van),
              _0x11f8be[_0x2223ba(0x182)]["traverse"](function (_0x4560a7) {
                const _0x225052 = _0x2223ba;
                if (_0x4560a7[_0x225052(0x1e9)]) {
                  (_0x4560a7["castShadow"] = !![]),
                    (_0x4560a7[_0x225052(0x1d6)] = !![]);
                  for (
                    let _0x584df1 = 0x0;
                    _0x584df1 < vanElement[_0x225052(0x1a2)];
                    _0x584df1++
                  ) {
                    if (_0x4560a7[_0x225052(0x167)] == vanElement[_0x584df1]) {
                      (_0x4560a7[_0x225052(0x1ad)][_0x225052(0x1cf)] = exrEnv),
                        selects[_0x225052(0x1a6)](_0x4560a7);
                      break;
                    } else {
                      if (_0x4560a7["name"] != _0x225052(0x16a)) {
                        selects["push"](_0x4560a7),
                          otherMeshes[_0x225052(0x1a6)](_0x4560a7),
                          (_0x4560a7[_0x225052(0x1ad)][_0x225052(0x1cf)] =
                            cubeRenderTarget["texture"]);
                        if (_0x4560a7["material"][_0x225052(0x1ca)])
                          _0x4560a7[_0x225052(0x1ad)][_0x225052(0x1ca)][
                            _0x225052(0x170)
                          ] = sRGBEncoding;
                        if (_0x4560a7[_0x225052(0x1ad)][_0x225052(0x184)])
                          _0x4560a7["material"][_0x225052(0x184)]["encoding"] =
                            sRGBEncoding;
                        if (
                          _0x4560a7[_0x225052(0x1ad)][_0x225052(0x1ca)] ||
                          _0x4560a7["material"]["emissiveMap"]
                        )
                          _0x4560a7["material"][_0x225052(0x161)] = !![];
                      }
                    }
                  }
                  (_0x4560a7[_0x225052(0x167)] == _0x225052(0x1b8) ||
                    _0x4560a7[_0x225052(0x167)] == _0x225052(0x14d)) &&
                    (_0x4560a7[_0x225052(0x1e4)] = ![]);
                  const _0x5ea241 = new _0x87ac58[_0x225052(0x19f)]()[
                    _0x225052(0x1d2)
                  ](scene);
                  return _0x2a4b3a["setSceneClipBox"](_0x5ea241), _0x4560a7;
                }
              }),
              cubeCamera["update"](renderer, scene);
          },
          undefined,
          function (_0x57e4b2) {
            const _0x45df6f = _0x24c8dc;
            console[_0x45df6f(0x1ac)](_0x57e4b2);
          }
        ),
        updateEnvironment(),
        cubeCamera["update"](renderer, scene);
      const _0x5700b3 = new GUI();
      _0x5700b3[_0x24c8dc(0x169)](_0x2a4b3a, "output", {
        Default: GTAOPass[_0x24c8dc(0x195)][_0x24c8dc(0x15a)],
        Diffuse: GTAOPass[_0x24c8dc(0x195)][_0x24c8dc(0x1c5)],
        "AO\x20Only": GTAOPass[_0x24c8dc(0x195)]["AO"],
        "AO\x20Only\x20+\x20Denoise":
          GTAOPass[_0x24c8dc(0x195)][_0x24c8dc(0x186)],
        Depth: GTAOPass["OUTPUT"][_0x24c8dc(0x15e)],
        Normal: GTAOPass[_0x24c8dc(0x195)][_0x24c8dc(0x193)],
      })["onChange"](function (_0x3242f7) {
        const _0xe89cef = _0x24c8dc;
        _0x2a4b3a[_0xe89cef(0x16f)] = _0x3242f7;
      });
      const _0x46221b = {
          radius: 0.2,
          distanceExponent: 1.85,
          thickness: 0x1,
          scale: 1.5,
          samples: 0x20,
          distanceFallOff: 0x1,
          screenSpaceRadius: ![],
        },
        _0x50f18e = {
          lumaPhi: 0xa,
          depthPhi: 0x2,
          normalPhi: 0x3,
          radius: 0.5,
          radiusExponent: 0x1,
          rings: 0x2,
          samples: 0x20,
        };
      _0x2a4b3a[_0x24c8dc(0x19c)](_0x46221b),
        _0x2a4b3a[_0x24c8dc(0x171)](_0x50f18e),
        _0x5700b3["add"](_0x2a4b3a, _0x24c8dc(0x1de))
          ["min"](0x0)
          [_0x24c8dc(0x1e5)](0x1)
          [_0x24c8dc(0x1e2)](0.01),
        _0x5700b3[_0x24c8dc(0x169)](_0x46221b, _0x24c8dc(0x1a3))
          [_0x24c8dc(0x17c)](0.01)
          [_0x24c8dc(0x1e5)](0x1)
          [_0x24c8dc(0x1e2)](0.01)
          [_0x24c8dc(0x1ea)](() => _0x2a4b3a[_0x24c8dc(0x19c)](_0x46221b)),
        _0x5700b3["add"](_0x46221b, _0x24c8dc(0x196))
          [_0x24c8dc(0x17c)](0x1)
          [_0x24c8dc(0x1e5)](0x4)
          [_0x24c8dc(0x1e2)](0.01)
          ["onChange"](() => _0x2a4b3a[_0x24c8dc(0x19c)](_0x46221b)),
        _0x5700b3[_0x24c8dc(0x169)](_0x46221b, _0x24c8dc(0x175))
          [_0x24c8dc(0x17c)](0.01)
          [_0x24c8dc(0x1e5)](0xa)
          [_0x24c8dc(0x1e2)](0.01)
          ["onChange"](() => _0x2a4b3a[_0x24c8dc(0x19c)](_0x46221b)),
        _0x5700b3[_0x24c8dc(0x169)](_0x46221b, _0x24c8dc(0x1a7))
          [_0x24c8dc(0x17c)](0x0)
          [_0x24c8dc(0x1e5)](0x1)
          [_0x24c8dc(0x1e2)](0.01)
          [_0x24c8dc(0x1ea)](() => _0x2a4b3a[_0x24c8dc(0x19c)](_0x46221b)),
        _0x5700b3["add"](_0x46221b, _0x24c8dc(0x163))
          ["min"](0.01)
          [_0x24c8dc(0x1e5)](0x2)
          [_0x24c8dc(0x1e2)](0.01)
          ["onChange"](() => _0x2a4b3a[_0x24c8dc(0x19c)](_0x46221b)),
        _0x5700b3[_0x24c8dc(0x169)](_0x46221b, _0x24c8dc(0x1d5))
          ["min"](0x2)
          [_0x24c8dc(0x1e5)](0x20)
          [_0x24c8dc(0x1e2)](0x1)
          [_0x24c8dc(0x1ea)](() => _0x2a4b3a[_0x24c8dc(0x19c)](_0x46221b)),
        _0x5700b3[_0x24c8dc(0x169)](_0x46221b, _0x24c8dc(0x1eb))[
          _0x24c8dc(0x1ea)
        ](() => _0x2a4b3a[_0x24c8dc(0x19c)](_0x46221b)),
        _0x5700b3[_0x24c8dc(0x169)](_0x50f18e, _0x24c8dc(0x1b2))
          [_0x24c8dc(0x17c)](0x0)
          ["max"](0x14)
          [_0x24c8dc(0x1e2)](0.01)
          [_0x24c8dc(0x1ea)](() => _0x2a4b3a[_0x24c8dc(0x171)](_0x50f18e)),
        _0x5700b3[_0x24c8dc(0x169)](_0x50f18e, _0x24c8dc(0x1b6))
          ["min"](0.01)
          [_0x24c8dc(0x1e5)](0x14)
          [_0x24c8dc(0x1e2)](0.01)
          [_0x24c8dc(0x1ea)](() => _0x2a4b3a[_0x24c8dc(0x171)](_0x50f18e)),
        _0x5700b3["add"](_0x50f18e, _0x24c8dc(0x1d0))
          [_0x24c8dc(0x17c)](0.01)
          [_0x24c8dc(0x1e5)](0x14)
          ["step"](0.01)
          [_0x24c8dc(0x1ea)](() => _0x2a4b3a[_0x24c8dc(0x171)](_0x50f18e)),
        _0x5700b3["add"](_0x50f18e, "radius")
          [_0x24c8dc(0x17c)](0x0)
          ["max"](0x20)
          [_0x24c8dc(0x1e2)](0x1)
          [_0x24c8dc(0x1ea)](() => _0x2a4b3a[_0x24c8dc(0x171)](_0x50f18e)),
        _0x5700b3[_0x24c8dc(0x169)](_0x50f18e, "radiusExponent")
          [_0x24c8dc(0x17c)](0.1)
          ["max"](0x4)
          [_0x24c8dc(0x1e2)](0.1)
          [_0x24c8dc(0x1ea)](() => _0x2a4b3a[_0x24c8dc(0x171)](_0x50f18e)),
        _0x5700b3[_0x24c8dc(0x169)](_0x50f18e, "rings")
          [_0x24c8dc(0x17c)](0x1)
          [_0x24c8dc(0x1e5)](0x10)
          ["step"](0.125)
          [_0x24c8dc(0x1ea)](() => _0x2a4b3a[_0x24c8dc(0x171)](_0x50f18e)),
        _0x5700b3["add"](_0x50f18e, _0x24c8dc(0x1d5))
          [_0x24c8dc(0x17c)](0x2)
          [_0x24c8dc(0x1e5)](0x20)
          [_0x24c8dc(0x1e2)](0x1)
          ["onChange"](() => _0x2a4b3a["updatePdMaterial"](_0x50f18e)),
        _0x5700b3[_0x24c8dc(0x169)](ssrParams, "enableSSR")["name"](
          _0x24c8dc(0x154)
        ),
        _0x5700b3[_0x24c8dc(0x169)](ssrParams, "groundReflector")[
          _0x24c8dc(0x1ea)
        ](() => {
          const _0x322dde = _0x24c8dc;
          ssrParams["groundReflector"]
            ? ((ssrPass[_0x322dde(0x1c1)] = groundReflector),
              (ssrPass[_0x322dde(0x1a9)] = selects))
            : ((ssrPass[_0x322dde(0x1c1)] = null),
              (ssrPass[_0x322dde(0x1a9)] = null));
        }),
        (ssrPass[_0x24c8dc(0x175)] = 0.018),
        _0x5700b3[_0x24c8dc(0x169)](ssrPass, "thickness")
          [_0x24c8dc(0x17c)](0x0)
          [_0x24c8dc(0x1e5)](0.1)
          [_0x24c8dc(0x1e2)](0.0001),
        (ssrPass[_0x24c8dc(0x192)] = ![]),
        _0x5700b3[_0x24c8dc(0x169)](ssrPass, _0x24c8dc(0x192)),
        _0x5700b3[_0x24c8dc(0x169)](ssrParams, _0x24c8dc(0x1b4))[
          _0x24c8dc(0x1ea)
        ](() => {
          const _0x264d3a = _0x24c8dc;
          controls["enabled"] = !ssrParams[_0x264d3a(0x1b4)];
        });
      const _0xc506ba = _0x5700b3[_0x24c8dc(0x1dd)]("more\x20settings");
      _0xc506ba[_0x24c8dc(0x169)](ssrPass, "fresnel")[_0x24c8dc(0x1ea)](() => {
        const _0x16f7ee = _0x24c8dc;
        groundReflector[_0x16f7ee(0x183)] = ssrPass[_0x16f7ee(0x183)];
      }),
        _0xc506ba[_0x24c8dc(0x169)](ssrPass, "distanceAttenuation")[
          _0x24c8dc(0x1ea)
        ](() => {
          const _0x58ac29 = _0x24c8dc;
          groundReflector[_0x58ac29(0x166)] = ssrPass[_0x58ac29(0x166)];
        }),
        (ssrPass[_0x24c8dc(0x16e)] = 0.3),
        (groundReflector[_0x24c8dc(0x16e)] = ssrPass[_0x24c8dc(0x16e)]),
        _0xc506ba[_0x24c8dc(0x169)](ssrPass, _0x24c8dc(0x16e))
          ["min"](0x0)
          [_0x24c8dc(0x1e5)](0.5)
          [_0x24c8dc(0x1e2)](0.001)
          [_0x24c8dc(0x1ea)](() => {
            const _0x596d8 = _0x24c8dc;
            groundReflector[_0x596d8(0x16e)] = ssrPass[_0x596d8(0x16e)];
          }),
        _0xc506ba["add"](ssrParams, _0x24c8dc(0x1a8))[_0x24c8dc(0x1ea)](() => {
          const _0xb190f0 = _0x24c8dc;
          ssrParams[_0xb190f0(0x1a8)]
            ? otherMeshes[_0xb190f0(0x181)](
                (_0x58e536) => (_0x58e536[_0xb190f0(0x1e4)] = !![])
              )
            : otherMeshes[_0xb190f0(0x181)](
                (_0x54af80) => (_0x54af80["visible"] = ![])
              );
        }),
        _0xc506ba[_0x24c8dc(0x169)](ssrPass, _0x24c8dc(0x159)),
        _0xc506ba[_0x24c8dc(0x169)](ssrPass, _0x24c8dc(0x16f), {
          Default: SSRPass[_0x24c8dc(0x195)]["Default"],
          "SSR\x20Only": SSRPass["OUTPUT"]["SSR"],
          Beauty: SSRPass[_0x24c8dc(0x195)][_0x24c8dc(0x1bb)],
          Depth: SSRPass["OUTPUT"][_0x24c8dc(0x15e)],
          Normal: SSRPass["OUTPUT"][_0x24c8dc(0x193)],
          Metalness: SSRPass["OUTPUT"][_0x24c8dc(0x15d)],
        })[_0x24c8dc(0x1ea)](function (_0x551ddc) {
          const _0x4d1308 = _0x24c8dc;
          ssrPass[_0x4d1308(0x16f)] = _0x551ddc;
        }),
        (ssrPass[_0x24c8dc(0x180)] = 0.5),
        (groundReflector["opacity"] = ssrPass[_0x24c8dc(0x180)]),
        _0xc506ba[_0x24c8dc(0x169)](ssrPass, _0x24c8dc(0x180))
          [_0x24c8dc(0x17c)](0x0)
          [_0x24c8dc(0x1e5)](0x1)
          [_0x24c8dc(0x1ea)](() => {
            const _0x223612 = _0x24c8dc;
            groundReflector[_0x223612(0x180)] = ssrPass[_0x223612(0x180)];
          }),
        _0xc506ba[_0x24c8dc(0x169)](ssrPass, _0x24c8dc(0x1cd)),
        _0x5700b3[_0x24c8dc(0x16c)](),
        _0x5700b3[_0x24c8dc(0x1a5)](),
        controls[_0x24c8dc(0x1a4)](_0x24c8dc(0x1b7), () => {
          const _0x535550 = _0x24c8dc;
          console[_0x535550(0x1c8)](_0x535550(0x14b), camera[_0x535550(0x1b1)]),
            console[_0x535550(0x1c8)](
              _0x535550(0x17b),
              controls[_0x535550(0x18a)]
            );
        });
    },
    updateEnvironment = () => {
      const _0x4420c5 = _0x4773e2,
        _0x46b025 = environments[_0x4420c5(0x179)](
          (_0x4f2a4c) =>
            _0x4f2a4c[_0x4420c5(0x167)] === initialState["environment"]
        )[0x0];
      console[_0x4420c5(0x1c8)]("environment:\x20", _0x46b025),
        getCubeMapTexture(_0x46b025)["then"](({ envMap: _0x230d70 }) => {
          exrEnv = _0x230d70;
        });
    },
    getCubeMapTexture = (_0x28a893) => {
      const _0x2e3fec = _0x4773e2,
        { id: _0xe861c6, path: _0x2064ba } = _0x28a893;
      if (_0xe861c6 === "neutral")
        return Promise[_0x2e3fec(0x19d)]({ envMap: neutralEnvironment });
      if (_0xe861c6 === "") return Promise[_0x2e3fec(0x19d)]({ envMap: null });
      return new Promise((_0x5ce076, _0x226a40) => {
        const _0x1e5b6a = _0x2e3fec;
        new EXRLoader()[_0x1e5b6a(0x1ba)](
          _0x2064ba,
          (_0x2bed22) => {
            const _0x593cd8 = _0x1e5b6a,
              _0x558a0c =
                pmremGenerator[_0x593cd8(0x1e0)](_0x2bed22)[_0x593cd8(0x1ab)];
            pmremGenerator[_0x593cd8(0x18d)](),
              console[_0x593cd8(0x1c8)](_0x593cd8(0x189), _0x558a0c),
              _0x5ce076({ envMap: _0x558a0c });
          },
          undefined,
          _0x226a40
        );
      });
    },
    animate = () => {
      const _0x2c6273 = _0x4773e2;
      requestAnimationFrame(animate),
        controls[_0x2c6273(0x1ae)](),
        TWEEN[_0x2c6273(0x1ae)](),
        ssrParams["enableSSR"]
          ? composer[_0x2c6273(0x17d)]()
          : renderer[_0x2c6273(0x17d)](scene, camera);
    };
  function onWindowResize() {
    const _0x3d3218 = _0x4773e2,
      _0x1c4bd8 = window[_0x3d3218(0x1c3)],
      _0x3286e9 = window[_0x3d3218(0x1e3)];
    camera["updateProjectionMatrix"](),
      renderer["setSize"](_0x1c4bd8, _0x3286e9),
      composer[_0x3d3218(0x1d8)](_0x1c4bd8, _0x3286e9),
      groundReflector[_0x3d3218(0x19e)]()[_0x3d3218(0x1d8)](
        _0x1c4bd8,
        _0x3286e9
      ),
      groundReflector[_0x3d3218(0x1c9)]["set"](_0x1c4bd8, _0x3286e9);
  }
  const onOverViewButton = () => {
    const _0x2e8335 = _0x4773e2;
    isGoMallMode = !isGoMallMode;
    if (isGoMallMode) {
      textButtonView = _0x2e8335(0x1c7);
      let _0x353e25 = {
        x: camera[_0x2e8335(0x1b1)]["x"],
        y: camera["position"]["y"],
        z: camera[_0x2e8335(0x1b1)]["z"],
      };
      new TWEEN[_0x2e8335(0x1b5)](_0x353e25)
        ["to"]({
          x: 0.33266818379163465,
          y: 0.4567208098842309,
          z: 0.009396602938231524,
        })
        [_0x2e8335(0x173)](() => {
          const _0x3f6cd9 = _0x2e8335;
          return (
            controls[_0x3f6cd9(0x18a)]["set"](
              -0.18035187854860613,
              0.34989708000472913,
              0.014436166392607084
            ),
            camera["position"][_0x3f6cd9(0x198)](_0x353e25)
          );
        })
        [_0x2e8335(0x178)]();
    } else {
      textButtonView = _0x2e8335(0x197);
      let _0x28f950 = {
        x: camera[_0x2e8335(0x1b1)]["x"],
        y: camera[_0x2e8335(0x1b1)]["y"],
        z: camera[_0x2e8335(0x1b1)]["z"],
      };
      new TWEEN[_0x2e8335(0x1b5)](_0x28f950)
        ["to"]({ x: 0x0, y: 0x3, z: -0x1 })
        [_0x2e8335(0x173)](() => {
          const _0x494fb4 = _0x2e8335;
          return (
            controls["target"]["set"](0x0, 0x0, 0x0),
            camera[_0x494fb4(0x1b1)][_0x494fb4(0x198)](_0x28f950)
          );
        })
        [_0x2e8335(0x178)]();
    }
  };
  onMount(() => {
    const _0x368a0c = _0x4773e2;
    init(),
      animate(),
      window["addEventListener"](_0x368a0c(0x176), onWindowResize);
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
