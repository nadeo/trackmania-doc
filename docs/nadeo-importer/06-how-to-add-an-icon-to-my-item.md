# How to add an icon to my Item

## Image file requirements

If you want to see an icon for your item in the Map Editor, you need to provide an icon file:

- The icon must be a .tga file (mandatory)

- The icon should have a resolution of 64x64 pixels (recommended)

You can create .tga files with a lot of bitmap image edition softwares, such as Gimp.

The resolution can be different than 64x64, but NadeoImporter will automatically transform it to a 64x64 image, embedded in the .Item.Gbx file.


## Link the image file to your item

Unlike the reference to the .MeshParams.xml in the .Item.xml, or the reference to the .fbx in the .MeshParams.xml, the reference to the icon cannot be explicit, it is always implicit:

- The icon must have the same base name as the .Item.xml file (but the extension must be .tga)

- The icon must be placed in a sub-folder called "Icon".

For instance:
> If you are trying to make an item from `{Trackmania_user_dir}\Work\Items\Samples\StaticObjects\Slope_Icon.Item.xml`
> 
> then the program will look for this file: `{Trackmania_user_dir}\Work\Items\Samples\StaticObjects\Icon\Slope_Icon.tga`


If the file is not provided, the item will not have any icon in the Map Editor.


## About file size

The icon will increase the size of the .Item.Gbx file by 16 Ko.

But when someone saves a map containing instances of your item, it will be **embedded in the .Map.Gbx file without its icon**, to save some memory (as the size of embeddable items is limited in .Map.Gbx files).

For example, if an item with an icon has a size of 20 Ko, it will only cost approximately 4 Ko in the .Map.Gbx file (even less than that, because embedded items are compressed).
