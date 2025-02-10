# URP

| shader    | urp                                                     | webgl              | note                                              |
| --------- | ------------------------------------------------------- | ------------------ | ------------------------------------------------- |
| PBR       | CustomPBR                                               | CustomPBR          | URP/Lit を Always Included Shaders にできない問題 |
| unlit     | `UniGLTF/UniUnlit`                                      | `UniGLTF/UniUnlit` |                                                   |
| MToon-1.0 | `VRM10/Universal Render Pipeline/MToon10` `from v0.112` | CustomMtoon        | WebGL + RuntimeLoad 問題                          |
| MToon-0.x | (built-in only)                                         | (built-in only)    | VRM-0.x 版の URP MToon 提供の予定はありません     |

## URP/Lit を Always Included Shaders にできない問題

`Universal Render Pipeline/Lit` は ShaderVariant が厖大で、 `Always Included Shaders` に登録することが非推奨です。

- https://github.com/vrm-c/UniVRM/pull/2498
- https://discussions.unity.com/t/urp-lit-sample-is-missing-all-shaders-in-webgl-build/863894/4

RuntimeLoad 向けではありません。

## WebGL + RuntimeLoad 問題

WebGL で RuntimeLoad する場合に Unity の ShaderVariant の解決がうまくいかないようです。

- https://github.com/vrm-c/UniVRM/issues/2548

## VRM-0.x のモデルを VRM-1.0 に変換ロードできます

[UniVRM10_Vrm10](/api/runtime-import/UniVRM10_Vrm10)
