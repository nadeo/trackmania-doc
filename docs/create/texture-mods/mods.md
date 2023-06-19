# Introduction

Using texture mods, you can totally change the appearance of the game - basically it lets you create custom textures for existing and custom blocks and items.

The limit is your imagination (and maybe the download speed of the player).

## Building Your Mod

1. To get started, you'll want to download the [base game texture files](https://mega.nz/file/9CNSQDLA#b0W1Q3enG7ZAPv0XQGWArhk3sIPHV0S483Ly8annqw4) (maintained by **Zai**). Extract these textures to a folder you can easily access and **don't touch the files besides copying them**; you can copy/paste the files you need later, keeping the originally extracted textures as they are.
2. [ModWork](/create/texture-mods/modwork) is an easy and fast way to see your mod locally as you work. Its biggest pro is that you don't have to restart your game every time you author a new texture. Just save the texture and alt-tab back into the game for instant updates!
3. Trackmania textures are based on the [PBR workflow](https://en.wikipedia.org/wiki/Physically_based_rendering). The way the textures are comprised is very common in other recent video games.<br>
For Trackmania mods, texture formats are stored as `.dds` files -  if you use Photoshop, the free tool [NVIDIA Texture Tools Exporter](https://developer.nvidia.com/nvidia-texture-tools-exporter) is perfect for authoring `.dds` textures; it also automatically creates [mipmaps](http://wiki.polycount.com/wiki/Mip_Mapping)!
Technically `.png` files are supported as well, but it's strongly recommended to stick to `.dds` - `.png` does not support mipmaps, which significantly improve how textures are shown/filtered at a distance.<br>
To get started, drag the texture you want to edit from the `ModWork` folder into an image editor of your choice and do your magic.
Check out the [Texture List](/create/texture-mods/texture-list) for a quick reference of the different texture formats.
If you're looking for creative commons-licensed textures to use, check out [this list of texture sites](https://docs.google.com/spreadsheets/d/1Z4UhjLRHEwsRsHRvMqhoyiOVN_KRT067SeFfTZCEmQc/edit?usp=sharing) (compiled by **BigthirstyTM**).

## Folder Structure

In order for the mod to work properly, your textures need to be placed in the proper directories.

- 📁 **ModName.zip:** A zip folder named however you choose.
    - 📁 **Image:** The majority of your textures go here.
    - 📁 **Moods:** Contains ambience textures, like the skybox.
    - **Car Effects:** Modified car textures sit directly in the zip, they don't have a subfolder.


## Applying And Hosting Your Mod

Mods are not contained in the maps they're associated with - instead the players will automatically try to download the mod when they open the map. To make sure it all goes smoothly, you'll want to make sure your mod is accessible and referenced correctly.

As a side note: Keep in mind players with slow connections may take a while to get the mod. If they're playing on a server, there's a chance they won't get the mod until they reload the map. So it's worth testing the map without the mod and making sure it's playable.

Once you're happy with your mod, check out the [mod hosting guide](/create/texture-mods/hosting) to see how you can make it available for other players.

## Troubleshooting

Texture mods can be a challenge - there's lots of things that can trip you up.
For answers to the most common questions, see the [mods troubleshooting page](/create/texture-mods/troubleshooting).
