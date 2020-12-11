# About Mesh, Shape and Mat Gbx files

Those who have been using the old NadeoImporter from Maniaplanet might wonder what happened to .Mesh.Gbx, .Shape.Gbx and .Mat.Gbx files that .Item.Gbx used to depend on.

The short answer is: "forget about them".
NadeoImporter and in-game editors usually produce .Item.gbx files which have no external dependencies (which means if you want to give this item to a friend you can juste give them the .Item.Gbx file, there is no other file it depends on).

However it is still possible to make .Mesh.Gbx, .Shape.Gbx or .Mat.Gbx files, but for very specific purposes. If you are curious, see the details below.


## Mesh and Shape files

You can create .Mesh.Gbx and .Shape.Gbx files with the following command line:
```sh
.\NadeoImporter Mesh {fbxSourceFileNameRelativeToWorkFolder}
```

But you cannot use those files to build a .Item.Gbx files (there are no more <Phy> and <Vis> tags in the .Item.xml, where there used to be an explicit link to .Mesh.Gbx and .Shape.Gbx files).

The only use of those files now is that you can import them in the Mesh Modeler (the in-game 3d mesh editor, that you can access through the map editor, by creating an item, and editing its mesh).


## Mat Gbx files

.Mat.Gbx are "custom material" files, which usually depend on several .dds "texture" files.

It is still possible to create such files from the Mesh Modeler, but it is generally not recommended, because the map editor will refuse to embed into the .Map.Gbx file any item which depends on a .Mat.Gbx file.

If you save your map containing those items with custom materials anyway, you will still be able to open it in the map editor, but not anywhere else (not even in Local > Play a map).

So there is not much point to create "custom materials", but it might still be useful to shoot nice videos from the Media Tracker (that you can access from the map editor).
