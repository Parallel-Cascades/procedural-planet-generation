# Welcome to the Documentation for Procedural Planet Generation

![Celestial Bodies](./assets/images/planets.png)

Procedural Planet Generation is a Unity framework for creating procedural celestial bodies through shaders with editor tools for texture baking and scripts for in-editor and runtime procedural generation.

Built with Shader Graph, VFX Graph, and Render Graph, this framework creates beautiful and detailed, lightweight, non-landable planets optimized for viewing from space. This is NOT a terrain generation tool - it focuses on procedural surface textures and visual effects rather than geometric terrain or heightmaps. It's perfect for space strategy games, solar system maps, background environments, and skyboxes.

[Get Started](./get-started.md){ .md-button .md-button--primary }

# Celestial Bodies

## Moons
![Moon](./assets/images/moons/hero.png)

Rocky planets with procedurally generated surface color and heightmap detail. Two crater layers and a masked ridge network modify color contrast and procedural normals for visual height variance.

### Customizable Features

| Feature | Options |
|-----------|---------|
| **Surface Color** | Procedural pattern scale, color gradient, saturation |
| **Heightmap & Contrast** | Height-based color contrast strength |
| **Craters** | Density, size and depth ranges |
| **Ridges** | Scale, density, width, mask noise scale, gain determines if crevices or ridges |
| **Normal Map Generation** | Global strength, granular multiplier for surface, ridge, craters |

## Earth-likes

![Earth-like](./assets/images/earth-like.png)
![Earth-like](./assets/images/earth-like-clouds-lights.png)

Procedurally generated terrestrial planets with landmasses, coastlines, and ice caps formed through layered noise fields. Heightmap-driven surface normals simulate relief. The heightmap also samples color gradients to create natural-looking terrain patterns. Oceans feature shallow and deep water regions with depth-based coloration.

Procedural animated clouds.

Toggleable city lights on dark side of planet.

Fresnel edge effect and post-processing glow for atmospheric effects.


| Feature                   | Options                                                                              |
| ------------------------- | ------------------------------------------------------------------------------------ |
| **Continents**            | Continent scale and overall land–ocean coverage ratio                                |
| **Ice Caps**              | Maximum ice cap extent based on elevation and ice edge falloff shaping               |
| **Surface Heightmap**     | Mountain scale, surface roughness, and coastline definition sharpness                |
| **Surface Color**         | Noise pattern scale, land color gradient, saturation, ocean deep/shallow coloration, height-based color contrast |
| **Oceans**                | Depth thresholds for shallow/deep regions and water surface smoothness (specular)    |
| **Normals**               | Global normal strength and per-layer contributions for mountains, ridges, and base noise |
| **Atmospheric Effects**   | Fresnel edge tint and atmospheric glow color, size, and falloff            |
| **Clouds**   | Size, density, normals, color, wave-like animation frequency and amplitude            |
| **City lights**   | Density for coastal vs inner cities, color, light power            |

## Gas Giants and Asteroid Rings

![Gas Giant with Ring](./assets/images/gas-giant-with-ring.png)

Procedurally generated gas giants feature dynamic, swirling cloud bands with animated storms and flowing patterns. Atmospheric effects with Fresnel edge glow and post-processing glow.

| Feature                 | Options                                                                                                        |
| ----------------------- | -------------------------------------------------------------------------------------------------------------- |
| **Color**       | Color gradient applied to cloud bands, saturation                                              |
| **Cloud Bands Pattern**        | Scale (number of bands), vertical band flow shape and scaling |
| **Storms**     | Density, size, twistiness, ovality, movement speed, appearance rate   |
| **Animation**           | Whorl movement speed and overall pattern flow rate                                                             |
| **Atmospheric Effects**   | Fresnel edge tint and atmospheric glow color, size, and falloff            |

Asteroid rings are procedurally generated spherically banded discs that rotate around a planet. Density and transparency vary across the bands, creating natural gaps and flowing patterns. Lighting overrides allow you to control visibility at acute viewing angles.

| Feature                | Options                                                                                                                                                |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Ring Shape**         | Inner and outer radius, edge fade strength, banding pattern defined by noise texture                                                                   |
| **Color**              | Gradient sampled along the ring pattern, overall saturation                                                                                            |
| **Ring Transparency**  | Alpha threshold controlling which regions of the ring are transparent                                                                                  |
| **Animation / Flow**   | Rotation speed of the ring pattern                                                                                                                     |
| **Lighting Overrides** | Two-sided lighting for transparency, minimum brightness level to avoid overly dark areas, light falloff sharpness to smooth shading at glancing angles |

## Stars

![Star](./assets/images/star.png)

Stars are always lit with a flowing, molten surface with HDR color variation and corona glow and VFX.

| Feature                     | Options                                                                                                                                     |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Molten Pattern**          | Domain warp scale and intensity, pattern scale, and flow speed driving the animated molten surface |
| **Color Sampling**          | Primary color gradient plus Q/R domain-warp modulation channels blended with HDR colors for complex multi-band color variation |
| **Corona Effects**  | Fresnel edge glow (color and power), unlit spherical glow density and falloff, VFX particle color, spawn rate (corona thickness), particle size, and turbulence intensity |
