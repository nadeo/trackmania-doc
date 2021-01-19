# How to create the MeshParams xml file

Just create an empty text file (which has the extension ".txt" by default) and change its extension by renaming it `{ItemName}.MeshParams.xml` (for example: `Slope_Base.MeshParams.xml`).

Open this file in your favorite text editor (for example: Notepad++), and copy-paste the following template:

```xml
<MeshParams MeshType="Static" Collection="Stadium" Scale="1" FbxFile="ItemName.fbx">
	<Materials>
		<Material Name="A" Link="Name1FromTheMaterialLib" Color="F00" PhysicsId="Name1FromThePhysicsIdLib" GameplayId="Name1FromTheGameplayIdLib" />
		<Material Name="B" Link="Name2FromTheMaterialLib" Color="F00" PhysicsId="Name2FromThePhysicsIdLib" GameplayId="Name2FromTheGameplayIdLib" />
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
						- `PhysicsId`: facultative (and not recommended). Overrides the way the cars will interact physically with the surface. You should not overuse this feature because it is usually a bad idea (for gameplay and fun) to have a surface looking like grass but behaving like dirt. You can find the list of possible values in the `PhysicsId library` below.
						- `GameplayId`: facultative. Setting a value different than `None` will add a special gameplay effect to the surface, like activating free wheeling or slow motion modes. Some of those gameplay effects such as `Turbo` or `ReactorBoost` are "oriented": the direction of this effect is automatically the local z-axis of the item. You can find the list of possible values in the `GameplayId library` below.

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


# PhysicsId library

Here is the list of all `PhysicsId` in the game.

Each one has a different effect on car grip and speed (it also affects sound and skid marks).

Each material has a default `PhysicsId` that you can see in `{Trackmania_exe_dir}\NadeoImporterMaterialLib.txt`, next to `NadeoImporter.exe` (see section [Download and install]).

You can override this default behavior with the `PhysicsId` attribute of the `Material` tag, but it is not recommended (see the description of this attribute above).

- `Asphalt`: the actual base material of TrackMania, used on every normal road and platforms
- `Concrete`: "base" material, but not used for base roads in TM !
- `Dirt`: used in dirt blocks
- `Grass`: used in the default grass of the stadium (not to be mistaken with Green surfaces) and as a speed penalty surface
- `Green`: used in synthetic grass platforms (not to be mistaken with Grass surfaces)
- `Ice`: used in the colorable CustomIce material
- `Metal`: used in black platform blocks
- `MetalTrans`: mostly used on screens
- `NotCollidable`: used for decals, to... not be collidable. But instead of using this PhysicsId, you should rather use the `_notcollidable_` prefix in your fbx objects, as described in section [How to create the fbx file].
- `Pavement`: used in the colorable CustomBricks material
- `ResonantMetal`: also used in black platform blocks, usually makes a noise on collision
- `RoadIce`: used in "bobsleigh" ice blocks
- `RoadSynthetic`: used in bump roads
- `Rock`: used in colorable CustomRock material
- `Rubber`: used on the sides of the roads, gives speed penalty when hit
- `Sand`: used as a speed penalty surface in dirt platform blocks
- `Snow`: used in colorable CustomSnow material and as a speed penalty surface
- `TechMagnetic`: not used in any game material, makes the car attracted to that surface
- `TechMagneticAccel`: not used in any game material, makes the car attracted to that surface and gives it a better acceleration while on it
- `TechSuperMagnetic`: not used in any game material, makes the car attracted strongly to that surface
- `Wood`: used in colorable CustomRoughWood material


# GameplayId library

Here are the values you can use for the `GameplayId` attribute of the `Material` tag:

- `Bumper`: makes the car bump a bit
- `Bumper2`: makes the car bump a lot
- `ForceAcceleration`: disables breaking until next Reset block or next checkpoint
- `Fragile`: makes the car sensitive to hard bumps and crashes, making it harder to handle and accelerate the more damages it takes. Only gets back to normal with a Reset Block
- `FreeWheeling`: entirely stops the engine until next Reset block or next checkpoint
- `NoGrip`: comparable to ice, but way less handling and no drift mechanic until next Reset block or next checkpoint
- `None`: no gameplay effect (this is the default value for all game materials)
- `NoSteering`: disables steering until next Reset block or next checkpoint
- `ReactorBoost`: activates flames at the sides of the wheels that push the car upwards or downwards for some time or until next Reset block (direction of ReactorBoost is along Z-axis: towards positive Z is ReactorBoost Up and towards negative is ReactorBoost Down)
- `ReactorBoost2`: same effect as `ReactorBoost`, but stronger
- `Reset`: disables any ongoing gameplay effects
- `SlowMotion`: slows down the behaviour of the car (but not the timer) for some time or until next Reset block
- `Turbo`: "yellow turbo" blocks, sudden burst of acceleration (direction of Turbo is North / along Z-axis)
- `Turbo2`: "red turbo" blocks, stronger burst of acceleration (direction of Turbo2 is North / along the Z-axis)

[Download and install]: ../01-download-and-install/
[How to create the fbx file]: ../03-how-to-create-the-fbx-file/
