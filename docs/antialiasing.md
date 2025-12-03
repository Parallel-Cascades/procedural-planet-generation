# Anti-Aliasing

Some shader effects might experience flickering when created with very large scale, like earth-like planet city lights or moon surface noise scale. Procedural normal maps will also have this problem if the normal strength is too large or the underlying noise is too high frequency.

[Baking](./baking-textures.md) the procedural shaders into static textures solves this issue fully.

If you want to keep using procedural shaders, one way to deal with this is with [filtering](filtering.md) in the shader. Another is to use camera antialiasing:

![TAA on Camera](./assets/images/anti-aliasing/camera-taa.png)

Temporal Anti-Aliasing (TAA) produces some of the best results with URP.