# Getting Started

## Requirements

This asset is built for the Universal Render Pipeline (URP). 

Visual Effect Graph is required to render the particle systems for the star corona VFX.

Unity 6 is required for the Render Graph API used in the Post-Processing planet atmosphere and Glow effects.

## Installation

To install this asset, import it from the Package Manager:

![Package Import Window](./assets/images/get-started/import-package.png)

The asset contents are split in three folders to ensure compatibility with other Parallel Cascades assets.

## Quick Setup

To add your first procedural planet to a scene, you can access the custom menu commands by right clicking inside the Hierarchy view. This automatically generates the materials and textures required by the procedural planet, creates a GameObject in the scene and adds the necessary scripts and references to it:

![Add Procedural Planet Menu Item](./assets/images/get-started/menu-item.png)

Once you click on an option, a save folder window will open:

![Save Folder](./assets/images/get-started/save-folder.png)

This is the folder where new planet assets will be saved - textures and materials. It is recommended to create a new one for each planet to keep your project tidy.

![Procedural Moon Inspector](./assets/images/get-started/procedural-moon-inspector.png)

After adding a procedural planet to the scene, use the Procedural Body component’s custom inspector button to generate randomized planet variants or to regenerate surface color and shape parameters.

For manual adjustments, modify the exposed material and gradient properties in the Procedural Body inspector, or edit the corresponding shader parameters directly.
Note that values set through the component override the underlying shader properties.




