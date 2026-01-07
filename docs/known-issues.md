# Known Issues

## 1. `ArgumentException: An item with the same key has already been added. Key: UnityEditor.Graphing.Edge`
When opening the default Earth-like shader. The shader graph file was corrupted somehow with the 1.0.3 update. You can still use the shader, but cannot make changes to the shader graph. A fix for this is coming soon.

## 2. Flickering with high-detail noise patterns when viewed from a distance.

See [Anti-Aliasing](./antialiasing.md) and [Filtering](./filtering.md). [Baked](./baking-textures.md) textures do not have this issue.

## 3. Cubemap Preview during baking showing a seam between faces

This is in fact a repeated face. This might happen if any changes have been made to the shader just prior to baking:

![Cubemap Face Bug](./assets/images/known-issues/cubemap-face-bug.png)

This only affects the preview image and will not carry over to the final rendered image and can be ignored.