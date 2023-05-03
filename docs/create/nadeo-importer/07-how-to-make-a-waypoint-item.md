# How to make a waypoint item

You can make items which will be considered by the game as "waypoints": a start line, a checkpoint, a finish line or a multi-lap start-finish line.

1. First you must add the Waypoint tag in the .Item.xml file, with the correct `Type` attribute ("Start", "Checkpoint", "Finish", "StartFinish"). See section [How to create the Item xml file] for more information.

2. Wether your item is a "Start", "Checkpoint", "Finish" or "StartFinish" waypoint, the .fbx file must contain exactly one object called `_socket_start`. The location of this object is all that matters (its faces are ignored): it will determine the position of the car when we spawn or respawn on this waypoint. 

3. If your item is a "Checkpoint", "Finish" or "StartFinish" waypoint, then the .fbx file must contain at least one object with prefix `_trigger_`. These objects will not be visible but the game will detect when the car goes through its faces and trigger the checkpoint / finish event when it happens.

[How to create the Item xml file]: ../05-how-to-create-the-item-xml-file/