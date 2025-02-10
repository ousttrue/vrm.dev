# MToon example

Unlit をベースにしてシェーディングは自作します。

[WebGL build](https://vrm-c.github.io/UniVRM/VRM10Viewer/)

## 仕様

https://github.com/vrm-c/vrm-specification/blob/master/specification/VRMC_materials_mtoon-1.0/README.ja.md#implementation

## BaseColor & ShadeColor

```
function linearstep( a: Number, b: Number, t: Number ): Number
  return saturate( ( t - a ) / ( b - a ) )
end function

let shading: Number = dot( N, L )
shading = shading + shadingShiftFactor
shading = shading + texture( shadingShiftTexture, uv ) * shadingShiftTexture.scale
shading = linearstep( -1.0 + shadingToonyFactor, 1.0 - shadingToonyFactor, shading )

let baseColorTerm: ColorRGB = baseColorFactor.rgb * texture( baseColorTexture, uv ).rgb
let shadeColorTerm: ColorRGB = shadeColorFactor.rgb * texture( shadeMultiplyTexture, uv ).rgb

let color: ColorRGB = lerp( shadeColorTerm, baseColorTerm, shading )
color = color * lightColor
```

> https://github.com/vrm-c/vrm-specification/blob/master/specification/VRMC_materials_mtoon-1.0/README.ja.md#implementation

### AlphaBlending & Cuttoff

### ShadingShift

TODO

## Emission

TODO

## NormalMap

TODO

## Outline

TODO

URP でマルチパスの方法が無いので法線拡大裏面法が使えません。擬似的な方法を使います。

## UV Animation

TODO

## Matcap

TODO

## RimLight

TODO
