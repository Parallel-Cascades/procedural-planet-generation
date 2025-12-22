# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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