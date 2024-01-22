# How to import an item

## File organization

The source assets (.fbx, .MeshParams.xml and .Item.xml files) must be placed in sub folders of `{Trackmania_user_dir}\Work\Items`.

The corresponding imported files (.Item.Gbx) will be created in sub folders of `{Trackmania_user_dir}\Items` (without `\Work`).

For instance:

- source assets:<br/>
  `{Trackmania_user_dir}\Work\Items\Samples\StaticObjects\Mesh\Slope_Base.fbx`<br/>
  `{Trackmania_user_dir}\Work\Items\Samples\StaticObjects\Mesh\Slope_Base.MeshParams.xml`<br/>
  `{Trackmania_user_dir}\Work\Items\Samples\StaticObjects\Slope_Base.Item.xml`

- imported file:<br/>
  `{Trackmania_user_dir}\Items\Samples\StaticObjects\Slope_Base.Item.gbx`

So you must create the source assets first.

The `Samples.zip` file that you can download in section [Download and install] contains examples of such files.

For more information about how to create and edit source assets, see the following sections:

- [How to create the fbx file]

- [How to create the MeshParams xml file]

- [How to create the Item xml file].

## Import command

To generate the .Item.Gbx File:

1. Open a command line window in your {Trackmania_exe_dir} folder. One quick way to do that is to maintain Shift and right-click on this folder in Windows Explorer, and then select "Open PowerShell window here" or "Open command window here" in the context menu.
2. Type the following command:

```powershell
.\NadeoImporter Item {Item.xml_Filename_Relative_To_WorkFolder}
```

For instance:

```powershell
.\NadeoImporter Item Items\Samples\StaticObjects\Slope_Base.Item.xml
```

## Notes

### Wildcard character

You can also use the wildcard character `*` to import several items at once.

For example, if you want to import all the items contained in `{Trackmania_user_dir}\Work\Items\Samples\StaticObjects`:

```sh
.\NadeoImporter Item Items\Samples\StaticObjects\*.Item.xml
```

### Icon

If you want your item to have an icon in the Map Editor (which is recommended), see section [How to add an icon to my item]

### Command arguments

The .MeshParams.xml and .fbx files do not appear in the arguments of this command line, because:

- .Item.xml contains a reference (either explicit or implicit: see tag `MeshParamsLink` in section [How to create the Item xml file]) to the .MeshParams.xml file

- .MeshParams.xml contains a reference (either excplit or implicit: see attribute `FbxFile` in section [How to create the MeshParams xml file]) to the .fbx file.

There is also a facultative command argument: `/LogMeshStats`.
This will give you some information about the fbx you are importing.

```powershell
.\NadeoImporter Item Items\Samples\StaticObjects\Slope_Base.Item.xml /LogMeshStats
```

### PowerShell vs classic command line

The `.\` before `NadeoImporter` is mandatory in PowerShell, but not in classic command line.

[Download and install]: ../01-download-and-install/
[How to create the fbx file]: ../03-how-to-create-the-fbx-file/
[How to create the MeshParams xml file]: ../04-how-to-create-the-meshparams-xml-file/
[How to create the Item xml file]: ../05-how-to-create-the-item-xml-file/
[How to add an icon to my item]: ../06-how-to-add-an-icon-to-my-item/
