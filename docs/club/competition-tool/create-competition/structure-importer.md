# Using the structure importer

Creating rounds can be done manually through the competition tool.

However, to save time on creating rounds, you can always use the structure importer and import a **structure object file** to quickly generate rounds based on your saved structure. This allows you to easily reuse bracket formats across multiple competitions.

If you would like to add rounds manually through the competition tool instead, go to [this page](./rounds.md).

## Reference

[Click here](../structure/index.md) to read a reference on structure objects and some examples.

## Importing your structure

In the "Structure format" step of the competition creation form, click on "Import structure". You will see the following text area.

![Structure screen](../../../img/competition-tool-structure-importer.png)

If you have a structure object ready for use, copy and paste the **raw JSON text** of your structure object. Click on "Next step structure" and you should have all of your rounds created!

From here on out, tweak the settings of each round (e.g. start/end times, round names, maps, script/plugin settings) to your preferences.

!!! important

    If your rounds collects participants from a qualifier round, don't forget to **tick the "Add qualifier" checkbox**. This will add a qualifier as the very first round of your competition.

## Saving structures for future use

After your competition is created, you can locate your structure object and save it for future use. From your competition's admin page, go to the **Structure** page. Here you will see all the rounds for your competition.

![Structure screen](../../../img/competition-tool-structure.png)

Click on the "Show Structure" button to view a JSON representation of your rounds. This is your **structure object**.

![Show structure](../../../img/competition-tool-structure-show.png)

To save the current structure, you can copy and paste everything in this field into a text file, and run it through the structure importer again the next time you create a new event.