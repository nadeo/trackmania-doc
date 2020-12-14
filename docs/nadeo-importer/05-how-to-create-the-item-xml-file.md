# How to create the Item xml file

Just create an empty text file (which has the extension ".txt" by default) and change its extension by renaming it `{ItemName}.Item.xml` (for example: `Slope_Base.Item.xml`).
Open this file in your favorite text editor (for example: Notepad++), and copy-paste the following template:

```xml
<Item Type="StaticObject" Collection="Stadium" AuthorName="YourAuthorName">
	<MeshParamsLink File="Mesh/ItemName.MeshParams.xml"/>
	<Waypoint Type="Checkpoint"/>
	<Pivots>
		<Pivot Pos="0 0 0"/>
		<Pivot Pos="0 0 -1.5"/>
		<Pivot Pos="0 0 1.5"/>
	</Pivots>
	<GridSnap HStep="8" VStep="2"/>
	<Levitation VStep="2" GhostMode="true"/>
	<PivotSnap Distance="0"/>
	<Options OneAxisRotation="true" ManualPivotSwitch="true"/>
</Item>
```

Then adapt it to your situation, according to the following explanations:

- `Item` tag is mandatory
	- attributes:
		- `Type` is mandatory and should not be changed ("StaticObject")
		- `Collection` is mandatory and should not be changed ("Stadium")
		- `AuthorName` should be changed to the name you want to be called in the Trackmania creative community :)
	- sub-tags:
		- `MeshParamsLink` tag is mandatory
			- attribute:
				- `File`: Facultative. The relative path of the .MeshParams.xml next to the .fbx file. If omitted, the .MeshParams.xml will be expected to have the same name as current .Item.xml file and to be located in a sub-folder "Mesh".
		- `Waypoint` tag is facultative. Use it only if you are making an item which is a special waypoint of the map, like a checkpoint or a finish line.
			- attribute:
				- `Type`: mandatory. Must be one of the following: "Start", "Checkpoint", "Finish", "StartFinish" ("StartFinish" is used for multilaps).
					- Note: this is not enough to make a valid waypoint item. See section [How to make a waypoint item] for more information.
		- `Pivots` tag is facultative. See section [Pivots and placement parameters] for more information.
			- sub-tags:
				- `Pivot`: put one Pivot tag for each pivot you want to add to your item.
					- attribute:
						- `Pos`: Position of the pivot, in the base of your mesh. (0,0,0) would be the same origin as in the fbx file.
		- `GridSnap` tag is facultative
			- attributes:
				- `HStep`: Facultative. A positive real value in meters (0 by default). See `Grid Horizontal Size` in section [Pivots and placement parameters] for more information
				- `VStep`: Facultative. A positive real value in meters (0 by default). See `Grid Vertical Size` in section [Pivots and placement parameters] for more information
		- `Levitation` tag is facultative
			- attributes:
				- `VStep`: Facultative. A positive real value in meters (0 by default). See `Fly Step` in section [Pivots and placement parameters] for more information
				- `GhostMode`: Facultative. A boolean value: "true" or "false" ("false" by default). See `Ghost Mode` in section [Pivots and placement parameters] for more information
		- `PivotSnap` tag is facultative
			- attribute:
				- `Distance`: Mandatory. A positive real value in meters, or the special value -1 (-1 by default). See `Pivot Snap Distance` in section [Pivots and placement parameters] for more information
		- `Options` tag is facultative
			- attributes:
				- `NotOnItem`: Facultative. A boolean value: "true" or "false" ("false" by default). See `Not On Object` in section [Pivots and placement parameters] for more information.
				- `OneAxisRotation`: Facultative. A boolean value: "true" or "false" ("false" by default).  See `Yaw Only` in section [Pivots and placement parameters] for more information.
				- `ManualPivotSwitch`: Facultative. A boolean value: "true" or "false" ("false" by default). See `Switch pivot manually` in section [Pivots and placement parameters] for more information.
				- `AutoRotation`: Facultative. A boolean value: "true" or "false" ("false" by default). See `Auto Rotation` in section [Pivots and placement parameters] for more information.

You should get something like this:

```xml
<Item Type="StaticObject" Collection="Stadium" AuthorName="NadeoSamples">
	<MeshParamsLink/>
	<GridSnap HStep="8"/>
	<Options OneAxisRotation="true"/>
</Item>
```

[How to make a waypoint item]: ../07-how-to-make-a-waypoint-item/
[Pivots and placement parameters]: ../08-pivots-and-placement-parameters/