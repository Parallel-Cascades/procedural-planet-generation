# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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