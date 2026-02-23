# Gas Giants
The best-looking technique for gas giants uses Custom Render Textures and a special shader graph for a flow simulation.
You can read more about it in the [Curl Gas Giants documentation page](curl-gas-giants-simulation.md).
Simpler, legacy shaders that directly generate the gas giant patterns are also available at: [Gas Giant Legacy Shaders](gas-giant-shaders.md).
Gas giant rings are covered here: [Gas Giant Rings](gas-giant-rings.md).

This asset requires Unity's Editor Coroutines Package in order to simulate curl simulations for the gas giants in Edit mode:
https://docs.unity3d.com/Packages/com.unity.editorcoroutines@1.0/manual/index.html
If you haven't installed this package when importing this asset, you can do so through the Package Manager.

## Quick Start
To add procedural gas giants to your scenes, right click inside your scene hierarchy to open the context menu and
from the very bottom of the list select "Parallel Cascades > Gas Giants > ..." and choose your desired procedural gas 
giant or ring.
This will then ask you for a folder to save your gas giant materials and resources in your project, and automatically
setup everything required for your gas giant simulation. 

## Sample Scenes - Found under "Parallel Cascades > Gas Giants > Samples"
- The Gas Giants with Flow Simulation scene demonstrates 4 pre-generated gas giants using custom render textures with flow simulation.
- The Custom Lighting sample scene demonstrates a basic solar system with a central star as the omnidirectional light. This
  uses a baked texture shader for the central star but shows custom lighting for the 4 gas giants in the scene. The DistanceToCameraForSimulation
  property of the ProceduralGasGiantFlowSimulation component on each gas giant is used to limit the flow simulation to only run when the gas giant is within a certain distance of the camera, improving performance.
  This allows for 4 gas giants to be on the screen simultaneously but only simulate flow when look at up-close.
- The Legacy Shader sample scene demonstrates older more rudimentary gas giant shaders that use noise masks and uv distortion
  instead of curl and custom render texture fluid simulation.