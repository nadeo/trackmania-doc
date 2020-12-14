# How to create the MeshParams xml file

Just create an empty text file (which has the extension ".txt" by default) and change its extension by renaming it `{ItemName}.MeshParams.xml` (for example: `Slope_Base.MeshParams.xml`).
Open this file in your favorite text editor (for example: Notepad++), and copy-paste the following template:

```xml
<MeshParams MeshType="Static" Collection="Stadium" Scale="1" FbxFile="ItemName.fbx">
	<Materials>
		<Material Name="A" Link="Name1FromTheMaterialLib" />
		<Material Name="B" Link="Name2FromTheMaterialLib" />
	</Materials>
</MeshParams>
```

Then adapt it to your situation, according to the following explanations:
- `MeshParams` tag is mandatory
	- attributes:
		- `MeshType` is mandatory and should not be changed ("Static")
		- `Collection` is mandatory and should not be changed ("Stadium")
		- `Scale` is facultative. You can set a value greater than 1 to make your item bigger, or less than 1 to make it smaller. But you should not set it to 0 or a negative value.
		- `FbxFile` is facultative. **If this attribute is omitted, then the fbx file is supposed to be next to this xml file, with the same name** (but a different extension: .fbx). If the fbx file has a different name or is in a different folder though, you have to put its relative path in this attribute.
	- sub-tags:
		- `Materials` tag is mandatory, because your mesh is supposed to have materials, that we have to link to the game material library at some point
			- sub-tags:
				- `Material`: You should put one Material tag for each material contained in your fbx file
					- attributes:
						- `Name`: the name of the material in the fbx file, that you have chosen when making your model in the 3d software you have used (Blender, 3ds Max...)
						- `Link`: the name of a material of Trackmania material library. **The list of library materials can be found in `{Trackmania_exe_dir}\NadeoImporterMaterialLib.txt`**, which was placed next to `NadeoImporter.exe` when you unzipped the importer files (see section [Download and install])
						- `Color`: facultative. If the linked material is a colorizable one, you can specify the color you want with a 3-digit or 6-digit hexadecimal color code (RGB or RRGGBB). For instance: F00 or FF0000 for red, 0F0 or 00FF00 for green, 00F or 0000FF for blue, FF0 or FFFF00 for yellow, etc.

You should get something like this:

```xml
<MeshParams MeshType="Static" Collection="Stadium">
	<Materials>
		<Material Name="Road1" Link="RoadDirt" />
		<Material Name="Road2" Link="RoadBump" />
		<Material Name="Wall" Link="TrackWall" />
	</Materials>
</MeshParams>
```

[Download and install]: ../01-download-and-install/
