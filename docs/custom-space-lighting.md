# Custom Space Lighting

## Introduction
You might require space lighting in your scene, where the light source is a central star that lights up all planets omni-directionally:

![Solar System](./assets/images/custom-lighting/solar-system.png)

One way to get space scene lighting is to use a Point light instead of a Directional light and manually adjust the light falloff in the URP source:

[https://docs.unity3d.com/6000.2/Documentation/Manual/urp/lighting/custom-lighting-change-light-falloff.html](https://docs.unity3d.com/6000.2/Documentation/Manual/urp/lighting/custom-lighting-change-light-falloff.html)

## Custom Shader Lighting
In order to avoid modifying URP source code and to give more fine-grained control over our space scene lighting, we use a different approach: Custom Shader Lighting. Check out the Custom Lighting Sample Scene to see how this is set-up.

Each of our shaders has a custom lighting variant that can be toggled with the Omnidirectional Space Lighting Keyword:
![Custom Lighting Toggle](./assets/images/custom-lighting/custom-lighting-toggle.png)

Toggling this on will make them use the Main Space Light Position and Main Space Light Color from our custom implementation instead of the main directional light. Place the Main Space Light component on the main star in the scene:

![Main Space Light](./assets/images/custom-lighting/main-space-light.png)

Now all planet or gas giant ring shaders that have Omnidirectional Space Lighting toggled on will receive lighting from this star.

For ease of use we have the Planet Shaders Global Settings script that manages all procedural shaders in the scene and can toggle custom space lighting in bulk:

![Planet Shaders Global Settings](./assets/images/custom-lighting/planet-shaders-global-settings.png)

Toggling Omnidirectional Space Lighting from here will affect all celestial bodies in the scene.

## Custom Shadows

In order to have realtime planet shadow with our custom space lighitng, we use an analytical shadow calculation - for now this only works for spherical planets. It allows us to have gas giant shadows on their rings, or have a moon shadow a planet and vice versa.

To set this up in your scene, use the Shadow Caster Buffer Manager:

![Shadow Caster Buffer Manager](./assets/images/custom-lighting/shadow-caster-buffer-manager.png)

Here you can specify which bodies should cast shadows. The Group ID integer property allows you to group up certain bodies and have them only shadow other bodies in their group, for example a Gas Giant only shades its own ring and moons, and inner system terrestrial planets do not shade eachother or outer gas giants.

Each procedural material has a Shadow Receiver Group ID property:

![Shadow Receiver Group ID](./assets/images/custom-lighting/shadow-receiver-group-id.png)

So in the custom space lighting example, the gas giant is set up as a shadow caster with group ID 1, and its ring's material property Shadow Receiver Group ID is set to 1 for it to receive shadow. 

The Earth and its moon shadow eachother, so they are both set up as shadow caster with group ID 2, and their materials' Shadow Receiver Group IDs are set to 2.