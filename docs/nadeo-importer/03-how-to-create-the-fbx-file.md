# How to create the fbx file

You can export .fbx files from external 3d editors such as Blender or 3ds Max.


## Materials

The file must contain meshes with materials.

You can name your materials however you want, but you must remember those names because you will have to bind them to actual Trackmania material names in the .MeshParams.xml file (see section [How to create the MeshParams xml file]).


## UVs

Uvs : for most of the static mesh materials, you will need 2 UV layers:

- a layer named `BaseMaterial` : base layer of the material, typically mapping your Diffuse texture.

- a layer named `Lightmap` : mandatory, needed for lightmap computation in Map Editor.

> For the `Lightmap` layer, the UV must not overlap, otherwise it will cause invalid lightmaps !

> Some materials will need only one of those two layers, as you can see in the file `{Trackmania_exe_dir}\NadeoImporterMaterialLib.txt`

In Blender, it's easy to name your layers.

In 3dsMax (which is classicaly index-based for layers), you have two options:

- use the `Channel Info` utility to name your layers (comes with 3dsmax, available in panel `Utility > More > Channel info`)

- or add the following information to the `User Defined Properties` (this is what `Channel Info` would do anyway):
```
MapChannel:1 = BaseMaterial
MapChannel:2 = LightMap
```


## Special object prefixes

The name of the objects contained in the .fbx file are ignored, except if they start with one of the following special prefixes:

- If the object name is `_socket_start`, its location is considered a special landmark, which will be interpreted as a spawn location for players. This is useful for all waypoint items (like checkpoint items): see section [How to make a waypoint item] for more information

- If the object name starts with `_trigger_` (for example: `_trigger_A`), its mesh will not be visible, and when a player will go through it, it will trigger a checkpoint or a finish event, depending on the type of item. See section [How to make a waypoint item] for more information.

- If the object name starts with `_notvisible_` (for example: `_notvisible_B`), its mesh will not be visible, but will be collidable (it's an "invisible wall" for players).

- If the object name starts with `_notcollidable_` (for example `_notcollidable_C`), its mesh will be visible but not collidable, the player will be able to go through it.

- If the object name starts with `_skip_`, its mesh will be completely ignored during the import process (might be useful to have landmarks in your 3d software that will not have any effect on the resulting .Item.Gbx).

[How to create the MeshParams xml file]: ../04-how-to-create-the-meshparams-xml-file/
[How to make a waypoint item]: ../07-how-to-make-a-waypoint-item/