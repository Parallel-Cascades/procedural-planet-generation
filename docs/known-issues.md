# Known Issues
More permanent solutions are being worked on for these issues, here are quick temporary solutions:

## 1. Flickering with high-detail noise patterns when viewed from a distance.

See [Anti-Aliasing](./antialiasing.md) and [Filtering](./filtering.md). [Baked](./baking-textures.md) textures do not have this issue.

Procedural normal filtering and distance-based LOD for the procedural shaders will be coming in a later update, which will completely remove the flickering.

## 2. Cubemap Preview during baking showing a seam between faces

This is in fact a repeated face. This might happen if any changes have been made to the shader just prior to baking:

![Cubemap Face Bug](./assets/images/known-issues/cubemap-face-bug.png)

 This only affects the preview image and will not carry over to the final rendered image and can be ignored.