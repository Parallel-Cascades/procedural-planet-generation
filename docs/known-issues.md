# Known Issues

## 1. Flickering with high-detail noise patterns when viewed from a distance.

See [Anti-Aliasing](./antialiasing.md) and [Filtering](./filtering.md). [Baked](./baking-textures.md) textures do not have this issue.

## 2. Cubemap Preview during baking showing a seam between faces

This is in fact a repeated face. This might happen if any changes have been made to the shader just prior to baking:

![Cubemap Face Bug](./assets/images/known-issues/cubemap-face-bug.png)

This only affects the preview image and will not carry over to the final rendered image and can be ignored.