# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.4.0] - 2026-03-24
Custom lighting improvements, bugfixes and new terrestrial planets

### Added
- Martian planet shader
- Toggle for asteroid instancing shader to allow use outside of belts
- Two new menu items for the above planet types
- Ambient lighting for custom lighting shaders
- Inline material inspector to Planet Glow and Corona Glow
- Shadow Receiver Group Id property for Gas Giant from Cubemap shader
- Manual menu items for setting camera orthographic mode and shader custom lighting mode under Tools/Parallel Cascades/Planet Generation

### Fixed
- Flow Simulation Gas Giant menu items weren't adding the planet glow component

## [1.3.2] - 2026-03-10
Editor performance improvement for flow simulation gas giants

### Fixed
- Poor editor performance with multiple flow simulation gas giants. Custom render texture initialization workaround used to re-run every frame in Edit mode, now runs only once.

### Changed
- Gas Giant cubemap initialization workaround reworked to avoid unnecessary reinitialization every frame in Edit mode.

## [1.3.1] - 2026-03-06
Minor fixes

### Added
- Orbit speed and rotation speed adjustment at runtime for Asteroid Belts

### Fixed
- Missing material reference from Asteroid Belts sample scene
- False warning when creating new asteroid belt for No LOD tiers defined resolved.

## [1.3.0] - 2026-03-05
Asteroid belts

### Added
- New sample scene with entire Solar System and asteroid belts.
- New Asteroid Belts with instancing shader - create via new menu item.

## [1.2.1] - 2026-02-23
Fixes for curl simulation gas giants.

### Fixed
- Flickering of gas giant whorl spheres

## [1.2.0] - 2026-01-20
New curl simulation gas giants added.

### Added
- Curl flow simulation for gas giants - new sample scenes, editor tools and shaders.
- Color palette support for Gas Giant and Ring generation - you can select the gradients from which random colors are picked during procedural generation.
- Validation for texture baking functions.
- Updated legacy gas giant shaders with normals and improved visuals.

### Fixed
- Moons procedural smoothness generation minor fix - now uses procedural normals.

### Removed
- Removed ProceduralGasGiantNew and GasGiantPatternNew components.
- Removed AsteroidRing.hlsl file - subgraph is used instead.
- Removed flow speed range randomization from Gas Giant procedural generation.

## [1.1.1] - 2026-01-20
Minor fixes

### Added
- New clouds procedural feature for Earth-like planets generation.
- Updated pdf documentation.

### Fixed
- Gas Giant Ring Menu item wasn't adding material and renderer.
- Default sizes for gas giant rings adjusted for new shader.

## [1.1.0] - 2026-01-19
New Gas Giants and Asteroid Rings, Custom lighting improvements, Orthographic camera support

### Added
- New Gas Giants - better looking with explicit vertical bands and much improved performance. Procedural smoothness.
- New Asteroid Rings - clearer ring bands separation and visual control over transparency. Procedural smoothness.
- Orthographic camera support for planet and corona glow.
- Smoothness and smoothness baking to moon shader.
- Improved custom lighting with multiple shadow casters support.
- Bake and Apply All Procedural Material Textures context menu
- New custom lighting shadow system that supports multiple planetary shadow casters.

### Fixed
- Gas Giants and Stars could not bake their procedural textures

### Changed
- Asteroid rings are now called "Gas Giant Rings" to avoid confusion with asteroid belts.

## [1.0.4] - 2026-01-08
Quick Fixes

### Fixed
- Earth-like shadergraph was corrupted: ArgumentException: An item with the same key has already been added. Key: UnityEditor.Graphing.Edge
- Runtime procedural generation scene now correctly generates new variants for both gas giant and asteroid ring.
- Removed unused ProceduralSphericalWhorls.hlsl file. Subgraph is used instead.

## [1.0.3] - 2025-12-23

### Added
- Fresnel Intensity property for randomly generated Earth-like planes.
- Procedural filtering for Earth-like city lights.
- Smoothness and emission baking for Earth-like planets.

### Changed
- Continent mask shader subgraph - extracted position and cubemap sampling logic outside of subgraph.

### Fixed
- Earth-likes runtime color generation was not applying color gradients correctly.
- Custom lighting shadows would stop updating after randomizing bodies in scene.

## [1.0.2] - 2025-12-15
Visual fixes.

### Added
- Improved filtering for surface noise and normals for Earth-likes and Moons. This removes an aliasing effect when viewing at a distance or at glancing angles. Effect on normals should be very noticeable.

## [1.0.1] - 2025-12-11
Minor fixes.

### Changed
- Asset split into Common folder and Core folder to support both full and lite versions.
- Color R and Q properties on StarGradientProceduralComponent are no longer serialized unnecessarily.

### Fixed
- Some sample scene UI was using TMP text. Changed to use standard Unity UI components.
- Procedural star generation through menu item sets renderer Shadow Casting Mode to Off.

## [1.0.0] - 2025-12-10

- Added
    - Initial release