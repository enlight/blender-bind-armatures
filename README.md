Blender *Bind Armatures* operator
======================

Overview
----------
This operator binds a simple game-ready armature to a Rigify or an advanced MakeHuman armature, please note that the latter has an inverted hips bone. The binding is done via Copy Transforms constraints on the deform bones of the armatures.

Usage
------
The operator can be invoked in **Object Mode** by selecting the simple armature, pressing the spacebar in the 3D View, and typing in **Bind Armatures**. A popup will then be displayed where you can select the more complex target armature from a drop-down list.

Custom MakeHuman Rigs
----------------------------
A simple game-ready rig called **game2** can be found in the **makehuman-rigs** directory of this repository, to use it copy it over to the **makehuman/data/rigs** directory in your MakeHuman installation directory, you'll then be able to select it from the **Rig presets** on the **Pose/Animate** tab in MakeHuman.

The **game2** rig has no face bones or palm bones, but does have fully articulated fingers. this rig can be bound to a Rigify rig exported from MakeHuman.

Further Customization
------------------------
Currently the operator is hard-coded to work with the **game2** armature, though it could be extended to support more armatures. If you'd like to add support for additional armatures you'll also need to create an appropriate rig preset for MakeHuman. If you use the **game2** rig preset as a starting point you can modify the .json file to:

- Add face bones by removing the relevant bones from the *"head"* entry in the **merge** section.
- Remove some finger bones by adding the relevant bones to the *"hand.L"* and *"hand.R"* entries in the **merge** section.
- Rename certain bones in the **bones** section, the format is *"original MakeHuman bone name" : "new bone name"*.