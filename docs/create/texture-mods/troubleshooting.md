# Mod troubleshooting

Working with mods doesn't always give you obvious errors, and you might not understand why something isn't working.
This page has a few troubleshooting tips for common grievances while creating mods.

## My final mod file is over 100MB! How do I size it down?

You can scale any texture as low and as high as you want. Most default textures can be saved as half their original resolution. Since using mods causes (mostly minimal) performance drops, it's good advice to not go beyond `2048x2048px` as your maximum texture resolution.
Remember: Textures you didn't edit do not need to be in the mod file. The game will use default textures (and resolution) for textures that are not in the mod file.

## My textures look full of artifacts or have strange colors after exporting

Make sure your `R_` texture is set up properly. If the original texture uses Metallic at all, it's best to keep it as `BC5` and edit the color channels accordingly.

## I went back to my game after exporting but it didn't update the texture in-game

Place your car or go back into the editor camera and it should force the update.

## My image editor is saying the file is already in use

Place your car or go back into the editor camera and export again.

## I can't change the mood setting in-game anymore

Mods overwrite the mood setting. Go back to the menu and hold `CTRL` while picking your map. There you can change the mood and select the mod.

## I want to convert an image to PBR textures, any way I can do that without professional editing software?

There are several tools and websites that you can use to transform pictures into PBR textures.
One you could use is [Materialize](http://www.boundingboxsoftware.com/materialize/).
Note: While these tools give decent results depending on the source image, it's nowhere near as accurate as a properly captured/created PBR texture. Feeding these tools an image will often result in approximations rather than true PBR textures, since they can't actually calculate depth or specular information from a simple picture. Essentially they're just filters.

## I've seen people create snowy rocks, how do I do this with a mod?

`CustomRock` is broken up in two materials; one for top-down projection and one for side projection. It's a technique called *Triplanar Projection Mapping*.
The top projection is controlled by the `CustomRock` material.
The side projection is controlled by the `CustomRock_pxz` material.
You can also modify the color difference overlay using `customrock_x2`.
Essentially, if you modify the top projection `CustomRock` material into having a white texture, you get snowy rocks.

## How can I pack my textures if I don't have an image editor that supports it?

The free tool [Channel-packing](https://github.com/Fidifis/Channel-packing) can be used to pack textures together (think Metallic/Roughness, Alpha).

## How do I use one of the [official stadium-less map bases](https://trackmania.exchange/mappack/view/1482) together with a mod?

You need to use the [Decoration Unlocker Openplanet plugin](https://openplanet.dev/plugin/decorationunlocker). Simply install the plugin, hold `CTRL` and click the map to open the editor, and you'll get a popup where you can pick your mod without the stadium!
