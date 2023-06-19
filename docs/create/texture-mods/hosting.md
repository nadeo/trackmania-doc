# Mod hosting guide

Once you're done in `ModWork` and you're happy with your changes, it's time to save your texture files as a proper mod.

## Package your mod

1. Create a `.zip` file of your `ModWork` directory and place it in `Trackmania\Skins\Stadium\Mod` - create the folder if you don't have it yet.
2. Ensure the `.zip` contains this structure: `\Image\imagetexturefiles.dds`.

## Upload your mod

Because the player will need to download the mod on the fly, you need to upload it to a commonly accessible place.

Generally, you can host your mod anywhere you want as long as it's a direct link. Here are the most common choices:

1. **Discord**: All files uploaded to Discord are publicly accessible - so you can just upload the mod in a private server and copy the file link (make sure you don't accidentally copy the message link instead!). Discord comes with a file size limit of 8MB by default and up to 500MB for Nitro users.
2. [**ManiaCDN**](http://upload.maniacdn.net): This is a free hosting service for the Trackmania community. All uploads are manually approved, so your mod might not be available immediately. But it's a cool service, especially since it's free and supported by the community.
3. [**Github**](https://github.com): Typically Github and other git hosts are meant for storing code and other technical assets, but you can also host generic files on there. Just make sure you can get a direct link to the file that's publicly accessible.
4. **Dropbox, Google Drive and other cloud storage providers**: These mostly work fine, but some of them might limit downloads after a certain number of accesses. If your mod gets used in a competition and only the first 1000 players are able to download it, that might be a problem.

## Reference your mod in your map

There's two ways to go about this. If you don't know which one you need, the direct link approach is probably fine.

Before you get started, **make sure your link is really pointing at the `.zip` file**.

### Direct link method

1. Copy the direct link to your mod you uploaded earlier.
2. Hold `CTRL` when opening your map in Trackmania and paste the link in the URL input field.
3. Save your map.

### Locator file method

1. Create a new text file and paste the direct link to your mod into it.
2. Save it as `YOURMODNAME.zip.loc` and place it in `Trackmania\Skins\Stadium\Mod`.
3. Hold `CTRL` when opening your map in Trackmania and point to the mod you placed in `Trackmania\Skins\Stadium\Mod`. It should already be in the little green day/sunset/night window in Trackmania as an easy pick.
4. Save your map.
