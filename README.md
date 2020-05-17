## What does it do?
Running the wizard will combine all the meshes on the chosen Game Object and its children that share the same material. If there is more than a single material in all sub-objects, sub-objects of result will be created so that each corresponds to a single material. A prefab will be created from the combined Game Object in the root of the Assets folder, with all the newly created merged meshes. The original will be set inactive in the scene and the combined Game Object will be put in its position.

## How does it work?
Put the provided script in any Editor folder. In the Menu Bar a new entry will appear ("E.S. Tools/Mesh Combine Wizard"). Picking this option will show the wizard dialog. The parent of objects to be combined should be assigned to a filed called _combine Parent_, which may be auto-assigned based on existing editor selection.

## Benefits:
* Lowers the amount of draw calls, usually dramatically.
* Does not need to draw all objects in the same batch regardless of wheter they are on screen or not, as opposed to static batching.
* Does not compromise workflow - no need to merge modular pieces outside Unity in a 3D tool. Quick iteration time when changing the combined design.
* Works with combined objects that have more than 64k verts.
* Does not compromise the original object's pivot point.

## Known limitations:
* Does not support objects with multiple materials on submeshes. Such meshes should be split in an external 3D tool, so that there is only a single material per mesh.
* Does not migrate components from the original other than MeshFilter and MeshRenderer.

## Versions:
2.0 - Added proper support for meshes with over 65K verts. Hardened the script and commented for public consumption.
1.0 - Original release






