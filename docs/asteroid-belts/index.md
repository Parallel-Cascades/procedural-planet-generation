# Asteroid Belts

## Overview

| Feature                                                   | Description                                                                                                                                                                                                                        |
|-----------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**Asteroid Shader**](asteroid-shader.md)                 | Shader Graph with vertex displacement for procedural shape and moon surface procedural normals for rocky appearance. Per-instance unique ID generation to produce unique asteroid shapes within an asteroid belt.                  |
| [**Asteroid Belt Component**](asteroid-belt-component.md) | Belt procedural generation - belt torus shape settings, asteroid color palettes and random generation. Handles edit mode and  runtime rendering through instancing. Performance optimization via mesh LOD system, frustum culling. |

Asteroid belts use a custom procedural shader with vertex displacement instancing to render 1000s of instances dynamically
at runtime with good performance.

![Asteroid Belt Editor](../assets/images/asteroid-belts/editor-asteroid-belt.png)

## Quick Start
To add a new asteroid belt to your scene, use the custom menu item to automatically set up the asteroid belt with
material, scripts and LOD meshes. Right click inside your scene hierarchy to open the context menu and
select "Parallel Cascades > Asteroid Belt".

![asteroid-belt-orbit-inspector.png](../assets/images/asteroid-belts/asteroid-belt-orbit-inspector.png)

This will create a game object in your scene with the Asteroid Belt component. Here you can adjust the whole asteroid belt appearance and animation - 
inner and outer radius, instance count and size ranges, animation speeds (orbit/rotation). 

To edit the appearance of asteroids - colors, surface normals, craters, displacement strength, you can adjust the asteroid material which is embedded in the Asteroid Belt inspector:

![asteroid-material-inspector.png](../assets/images/asteroid-belts/asteroid-material-inspector.png)


