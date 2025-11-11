# Post-processing Glow Effect

Stars and planets in space look more natural with a 'glow' around them. This is separate from a traditional bloom glow effect, as seen in the comparison below. For gas giants and earth-like planets, the glow could be parts of the visible atmosphere fading out into space.

![Gas Giant Glow](./assets/images/post-processing-glow/gas-giant-glow.png)
/// caption
The light-blue glow around the edges of the gas giant is fully adjustable through the 'Planet Glow' component.
///

This is implemented through a Render Graph post-processing effect with a custom render pass and Fullscreen shader.
Relevant scripts are 'PostFXGlowEffect', 'PlanetGlow' and 'StarCorona'. Planets created through the custom menu items have these setup automatically. These require a suitable material attached, see the 'Planet Glow' and 'Star Corona' shaders:
![Glow Shaders](./assets/images/post-processing-glow/shaders.png)

Planet Glow is occluded by light direction and only shows up on the bright side of planets, whereas Star Corona glow is omni-directional.

## Post processing glow and Bloom
The glow effect around planets can be achieved in two ways:

- Custom Render Pass Post-Processing Effect
- URP Bloom

![Corona Glow Comparisons](./assets/images/post-processing-glow/glow-comparison.png)
/// caption
**Glow Comparisons:** 1. Glow disabled  2. Bloom Glow  3. PostFX Glow  4. PostFX Glow
///

For best visual fidelity, we recommend using both the Star Corona or Planet Glow post-processing effect and enabling bloom in the URP volume.