# Download and install

## How to install Nadeo Importer

First download the **importer zip** file, and also the **sample zip** file if you are interested (see below for the download links).

The importer must be unzipped in the `{Trackmania_exe_dir}` folder, which is the folder that contains `Trackmania.exe`, typically `C:\Program Files\Ubisoft\Ubisoft Game Launcher\games\Trackmania` or `C:\Program Files\Trackmania`.
You might neeed administrator rights to unzip and place the importer files in there.

> This will add some files to your `{Trackmania_exe_dir}` folder, but the most important one is `NadeoImporter.exe`.
> 
> See section [How to import an item] to learn how to use this executable properly.

The sample files are not mandatory, but provide examples that can help you: you can unzip them in the `{Trackmania_user_dir}` folder, which is typically `{My Documents}\Trackmania`.
This will create the folder `{Trackmania_user_dir}\Work\Items\Samples` and fill it with source assets, ready to be imported.


## Current release

**Importer zip**: <https://nadeo-download.cdn.ubi.com/trackmania/NadeoImporter_2022_07_12.zip>

**Sample zip**: <https://nadeo-download.cdn.ubi.com/trackmania/NadeoImporterSamples_2021_01_19.zip>


## Changelog

- 2020/12/15: Initial release
- 2021/01/19: Add support for GameplayId (Turbo, Slow motion, etc.), and also PhysicsId
- 2021/03/24: Fix crashes linked to wrong UV mappings imported via Nadeo Importer, and detect the issue when importing
- 2021/04/23: Add CustomMetalPaint in the MatLib
- 2021/07/07: Update MaterialLib, PhysicsIds and GameplayIds with new materials from the June 2021 update
- 2021/10/15: Fix MaterialLib (BaseMaterial UVs were used for Lightmap in CustomXyz materials), fix bugs (wrong return code + omitted FbxFile attribute in MeshParams.xml was not handled correctly)
- 2022/07/12: GlassWaterWall is no longer invisible, added materials ("CustomModAddSelfIllum", "CustomModSelfIllumSimple", Chrono materials, "PlatformDirt_DecoHill2", "PlatformIce_DecoHill2"), fixed blur issues on the "CustomModSelfIllum" material, added second version of each "CustomMod..." material, fixed the behaviour when using both `_notvisible_` or `_notcollidable_` and Lods.

## All releases

**Importer zip**:

- <https://nadeo-download.cdn.ubi.com/trackmania/NadeoImporter_2020_12_15.zip>
- <https://nadeo-download.cdn.ubi.com/trackmania/NadeoImporter_2021_01_19.zip>
- <https://nadeo-download.cdn.ubi.com/trackmania/NadeoImporter_2021_03_24.zip>
- <https://nadeo-download.cdn.ubi.com/trackmania/NadeoImporter_2021_04_23.zip>
- <https://nadeo-download.cdn.ubi.com/trackmania/NadeoImporter_2021_07_07.zip>
- <https://nadeo-download.cdn.ubi.com/trackmania/NadeoImporter_2021_10_15.zip>
- <https://nadeo-download.cdn.ubi.com/trackmania/NadeoImporter_2022_07_12.zip>

**Sample zip**:

- <https://nadeo-download.cdn.ubi.com/trackmania/NadeoImporterSamples_2020_12_15.zip>
- <https://nadeo-download.cdn.ubi.com/trackmania/NadeoImporterSamples_2021_01_19.zip>


[How to import an item]: ../02-how-to-import-an-item/
