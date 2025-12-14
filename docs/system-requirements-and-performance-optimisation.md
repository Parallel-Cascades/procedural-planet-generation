# System Requierements and Performance Guide

This asset relies on complex procedural shaders to generate stars, gas giants, and planetary surfaces in real time on the GPU. While this enables highly detailed and unique visuals, it also comes with a GPU cost.

### Screen coverage impact
GPU cost increases as a larger portion of the screen is occupied by procedural bodies. Screen resolution also has a significant impact on performance: higher resolutions involve substantially higher pixel counts, meaning  (4K) rendering is considerably more demanding than 1080p.

In practical terms: The closer your camera gets to a planet and the higher your screen resolution, the worse the performance gets.

### Why Procedural Shaders Are GPU-Intensive

The shaders use expensive noise functions. Stars and gas giants are the most performance-intensive bodies because they use multiple layers and effects of high-frequency domain warped noise to get the flowing effect, and they apply it multiple times for procedural filtering to reduce aliasing at long viewing distances.

Other bodies such as asteroid rings, moons, and Earth-like planets use simpler, lower-detail noise functions. As a result, they are considerably less demanding and typically do not represent a performance bottleneck.

## Expected Performance and GPU Benchmarks

The asset has been benchmarked using worst-case scenarios, specifically when **stars or gas giants occupy the entire screen**.

- **RTX 3060**
    - 1080p: **60 FPS**

- **RTX 4060**
    - 1080p: **120 FPS**

For consistent and comfortable **4K gameplay**, **RTX 3080–class GPUs or higher** are recommended.

![Gas Giant Performance](./assets/images/performance/gas-giant-performance.png)

*Performance at 1080p with RTX 3060*

### Performance Test Steps

- Isolate object you're having performance issues with so that it's the only object you're viewing with the camera.
- Monitor FPS and GPU utilization when viewing at various distance (the distances you'll be viewing it at in your game)
- Compare editor performance vs build performance vs the expected benchmarked performance above.

## Utilise Texture baking when performance is critical (Paid version only)

The most effective way to eliminate performance issues is to [bake procedural materials to textures](./baking-textures.md). This converts the GPU-heavy procedural evaluation into standard texture sampling, drastically reducing runtime cost. 

## Troubleshooting Performance Issues

### Filtering Detail

There's a filtering detail shader property in the material inspector of gas giant and star materials. This parameter smooths visual aliasing when the object is viewed from far away, basically calculating multiple samples of the noise function per each pixel. If you're viewing your objects at very close distances, you can set this value to 0 to disable procedural filtering and improve performance.

![Filtering Property](./assets/images/performance/filtering.png)

### Reducing shader detail

For developers comfortable with shader modification, a property directly in the shader can be altered:

![NumLayers Shader Graph](./assets/images/performance/numLayers.png)

Within the Shader Graph for both procedural materials, you will find the domain warping nodes. These are the most computationally expensive parts of the shader. Each uses an internal `NumLayers` parameter, which controls how many times the effect is applied at progressively smaller scales.

This parameter is intentionally not exposed in the material inspector:

- Increasing it significantly can severely impact performance.
- Reducing it too far can result in visually poor output.

However, advanced users may choose to expose and tune thеse values manually, gaining a small performance boost in exchange for worse visual quality.
