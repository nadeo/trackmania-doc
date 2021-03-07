# Parallax Signs

**Parallax Signs** are ZIP-files containing a couple of `.dds` files ("Direct Draw Surface") and a `Skin.json` file. 

## Create your DDS files

First you need a drawing program that allows you to draw your image in mutiple layers. Choose any you are comfortable with like Photoshop, gimp, paint.NET, Krita, etc.. 

Parallax signs come in 3 different formats: 1x1, 2x1, and 4x1. Make sure to choose the dimensions of your image to fit one of these formats. (e.g. 1024x256,1024x512, 1024x1024). 

**Note:** Parallax signs allow for a *maximum* of 8 layers.

Once you have drawn your image, export each layer into a separate `.dds` file. If your program doesn't support exporting to `.dds`, just export each layer as `.png` and convert those files to `.dds` via a [png to dds conversion tool](https://www.aconvert.com/image/png-to-dds/). Make sure to name your files in a way that you easily remember their order from foreground to background.


## Create your Skin.json file

The Skin.json file is a simple text file. You can open and edit it with any text editor that can open .txt files (like Notepad). It looks something like this:


```json
{
    "ClassId": "Parallax",
    "Layers" = [
        {
            Name = "Layer1.dds",
            Depth= "50"
        },
        {
            Name = "Layer2.dds",
            Depth= "100"
        },
        {
            Name = "Layer3.dds",
            Depth= "500"
        },
        {
            Name = "Layer4.dds",
            Depth= "1000"
        }
    ]
}
```

In this example `Layer1.dds` is the name of the file displayed in the foreground and `Layer4.dds` is the name of the file displayed all the way in the background. Additionally to the order each Layer gets a property `Depth`. This indicates how "far away" the layer is supposed to be. This is what will cause the parallax effect ingame.

**Note:** You can choose any Depth you like for every layer, even higher values for layers in the foreground and lower valuers for layers in the background.

## Create and use the Parallax File

Once you have created both your .dds files and our Skin.json file, select all the files and put them into a .zip file. Depending on the format you chose for your parallax sign, save that zip file to one of these folders (if they don't exist, create them):

- `Documents\Trackmania\Skins\Any\Advertisement1x1`
- `Documents\Trackmania\Skins\Any\Advertisement2x1`
- `Documents\Trackmania\Skins\Any\Advertisement4x1`

Now start (or restart!) Trackmania, go into the map editor, place a sign and select the `Skin Mode (F5)`. Click in the sign you placed and your parallax sign should be selectable from the menu.

**Note:** Selecting a sign or iamge from your local disc does *NOT* make it available to other players who download and play your map. In order to do that you need to upload your file somewhere (like dropbox, Google Drive, or [ManiaCDN](http://upload.maniacdn.net/)) and then create a locator file (.loc) for your parallax sign. (The locator file for `MyParallax.zip` must be named `MyParallax.zip.loc` and contains a single line with the url where the zip file can be downloaded from)