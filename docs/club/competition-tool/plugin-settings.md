# Competition plugin settings

Below is a reference of plugin settings available to use on the competition tool.

!!! warning "Be careful with value types"

    Each server setting has its specific type. If you input these values into the Round settings screen, it will be automatically converted to the selected type.

    For example, if you would like to set a setting value to an empty string (`""`), you need to leave the value field blank.

## Ads

Display a carousel of images.

| Setting name  | Type   | Default value | Description                                                                      |
| :------------ | :----- | :------------ | :------------------------------------------------------------------------------- |
| S_AdImageUrls | String | `""`          | Urls separated by a pipe character (`\|`).<br/>Add a value to enable the plugin. |

## Qualifier

Settings used for qualifiers (round challenges).

| Setting name          | Type    | Default value | Description                                                                                     |
| :-------------------- | :------ | :------------ | :---------------------------------------------------------------------------------------------- |
| S_UsePlayListComplete | Boolean | `False`       | Complete the challenge when the map playlist is over for the first time (forbid playlist loop). |

## Competition whitelist

Allow only the players registered to a competition to join a server.

| Setting name                    | Type    | Default value | Description            |
| :------------------------------ | :------ | :------------ | :--------------------- |
| S_UseCompetitionWhitelistPlugin | Boolean | `False`       | Enable the plugin.     |
| S_CompetitionId                 | String  | `""`          | ID of the competition. |

## Match management

Automatically enabled for all matches.

| Setting name                      | Type    | Default value | Description                                                                                                                                                                                                                               |
| :-------------------------------- | :------ | :------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| S_AutoStartMode                   | String  | `""`          | Possible values:<br/>- `""`: disabled <br/>- `"delay"`: automatically start the match at start date + delay <br/>- `"light"`: the match starts automatically right away after the server starts.                                          |
| S_AutoStartDelay                  | Integer | `600`         | Delay in seconds used by the "delay" mode.                                                                                                                                                                                                |
| S_PickBanStartAuto                | Boolean | `False`       | Automatically start a Pick & Ban phase during the match start time.                                                                                                                                                                       |
| S_PickBanOrder                    | String  | `""`          | Sequence of string separated by a comma. Starting with "p" for pick or "b" for ban, followed by ":" and a number representing team position, player position or "r" for random (e.g. "b:1,b:0,p:0,p:1,p:r").<br/>See more examples below. |
| S_EnableReadyManager              | Boolean | `True`        | Do not depends on players readiness to automatically start the match                                                                                                                                                                      |
| S_UseAutoReady                    | Boolean | `False`       | A connected player is automatically considered ready                                                                                                                                                                                      |
| S_ReadyStartRatio                 | Integer | `1.0`         | Minimum value the ratio “ready players”/“all players” must reach to start the match                                                                                                                                                       |
| S_ReadyMinimumTeamSize            | Integer | `1`           | The minimum number of members a team needs to be considered ready                                                                                                                                                                         |
| S_DisableForceSpectatorOnComplete | Boolean | `False`       | Do not force all players in spectator mode when the match is over                                                                                                                                                                         |

!!! example "Examples for Match autostart"

    Start the match when all players are ready for the match, with 10-minute delay tolerance:

    ```
    S_AutoStartMode = delay
    S_AutoStartDelay = 600
    ```

!!! example "Examples for S_PickBanOrder"

    Let's say Team A and Team B are participating in a match. Since Team A has the higher seed, they're listed first in the match participants list.

    ![Team A and Team B listed in the match participants list.](../../img/competition-tool-pickban-example.png)

    Our pick and ban order is as follows.

    Lower&nbsp;seed&nbsp;ban
    -> Higher&nbsp;seed&nbsp;ban
    -> Higher&nbsp;seed&nbsp;pick
    -> Lower&nbsp;seed&nbsp;pick
    -> Lower&nbsp;seed&nbsp;pick
    -> Higher&nbsp;seed&nbsp;pick
    -> Higher&nbsp;seed&nbsp;ban
    -> Lower&nbsp;seed&nbsp;ban
    -> Random&nbsp;pick

    Since we already know that the higher seeded team is at position `0`, and the lower seeded team is at position `1`, we can set the `S_PickBanOrder` settings as follows:

    ```
    b:1,b:0,p:0,p:1,p:1,p:0,b:0,b:1,p:r
    ```

    The same can be done for solo competitions, where there can be more than 2 participants in a match.

    ```
    b:3,b:2,b:1,b:0,p:0,p:1,p:2,p:3
    ```

    The above setting can be read as follows: "start the ban phase from the lower seed to higher seed, then run the pick phase in reverse"

## Message timer

Send a message in the chat every 75 seconds.

| Setting name   | Type   | Default value | Description                                            |
| :------------- | :----- | :------------ | :----------------------------------------------------- |
| S_MessageTimer | String | `""`          | The message to send. Add a value to enable the plugin. |

## Minimum rank

Display a popup and UI in-game to inform the players about the minimum rank required to qualify for the next round.

| Setting name                 | Type    | Default value | Description                        |
| :--------------------------- | :------ | :------------ | :--------------------------------- |
| S_UsePlayerMinimumRankPlugin | Boolean | `False`       | Enable the plugin.                 |
| S_MinimumRank                | String  | `0`           | The rank to reach to be qualified. |

## Time limit

Limit the duration a player can stay on a server.

| Setting name         | Type    | Default value | Description                                                                                                    |
| :------------------- | :------ | :------------ | :------------------------------------------------------------------------------------------------------------- |
| S_UseTimeLimitPlugin | Boolean | `False`       | Enable the plugin.                                                                                             |
| S_TimeLimitDuration  | Integer | `300`         | The duration a player can stay on the server in seconds, based on the player's first connection to the server. |

## Trackmania UI

| Setting name             | Type   | Default value | Description                                                                |
| :----------------------- | :----- | :------------ | :------------------------------------------------------------------------- |
| S_TrackmaniaUIProperties | String | `""`          | **Deprecated.** The UI properties to hide. Add value to enable the plugin. |

!!! example "Example of a valid S_TrackmaniaUIProperties value"

    See all available options in [this page](https://github.com/maniaplanet/script-xmlrpc/blob/master/XmlRpcListing.md#trackmaniauiproperties).

    ```xml
    <ui_properties><round_scores visible='false'/></ui_properties>
    ```
