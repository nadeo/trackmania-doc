#Competition plugin settings

## Ads
Display a carousel of images

| Setting name   | Default value  | Description                                                            |
|:---------------|:---------------|:-----------------------------------------------------------------------|
 | S_AdImageUrls  | ""             | Urls separated by a pipe character `\|`. <br/> Add a value to enable plugin |

## Challenge
Automatically available for all challenges.

| Setting name          | Default value  | Description                                                                                     |
|:----------------------|:---------------|:------------------------------------------------------------------------------------------------|
| S_UsePlayListComplete | False          | Complete the challenge when the map playlist is over for the first time (forbid playlist loop)  |
 

## Competition whitelist
Allow only the players registered to a competition to join a server

| Setting name                     | Default value  | Description                                                                                     |
|:---------------------------------|:---------------|:------------------------------------------------------------------------------------------------|
| S_CompetitionId                  | ""             | Id of the competition                                                                           |
| S_UseCompetitionWhitelistPlugin  | False          | Complete the challenge when the map playlist is over for the first time (forbid playlist loop)  |


## Match management
Automatically enabled for all matches

| Setting name                        | Default value | Description                                                                                                                                                                                         |
|:------------------------------------|:--------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| S_AutoStartMode                     | ""            | Possible values :<br/> “” : disabled <br/> **“delay”** : automatically start the match at start_date + delay <br/> **“light”** : the match starts automatically right away after the server starts  |
| S_AutoStartDelay                    | 600           | Delay in seconds used by the "delay" mode                                                                                                                                                           |
| S_PickBanStartAuto                  | False         | Automatically start a pick&ban phase 10 minutes before the match start date                                                                                                                         |
| S_PickBanOrder                      | ""            | Use "p" for pick, "b" for ban. Use player position, team position, or "r"(random) to choose which team or player will pick or ban a map. ex: "p:1,b:0,p:0,b:1,p:r"      
| S_EnableReadyManager                | True          | Do not depends on players readiness to automatically start the match                                                                                                                                |
| S_UseAutoReady                      | False         | A connected player is automatically considered ready                                                                                                                                                |
| S_ReadyStartRatio                   | 1.0           | Minimum value the ratio “ready players”/“all players” must reach to start the match                                                                                                                 |
| S_ReadyMinimumTeamSize              | 1             | The minimum number of members a team needs to be considered ready                                                                                                                                   |
| S_DisableForceSpectatorOnComplete   | False         | Do not force all players in spectator mode when the match is over                                                                                                                                   |

## Message timer
Send a message in the chat every 75 seconds

| Setting name            | Default value  | Description                                            |
|:------------------------|:---------------|:-------------------------------------------------------|
| S_MessageTimer          | ""             | The message to send. <br/> Add value to enable plugin. |

## Minimum rank
Display a popup to inform the players about the minimum rank to reach

| Setting name                 |  Default value  | Description                        |
|:-----------------------------|:---------------:|:-----------------------------------|
| S_UsePlayerMinimumRankPlugin |      False      | Enable the plugin                  |
| S_MinimumRank                |        0        | The rank to reach to be qualified  |


## Time limit
Limit the duration a player can stay on a server. <br>
The limit is based on the player’s first connection to the server.

| Setting name         | Default value  | Description              |
|:---------------------|:---------------|:-------------------------|
| S_UseTimeLimitPlugin | False          | Enable the plugin        |
| S_TimeLimitDuration  | 300            | The duration in seconds  |

## Trackmania UI

| Setting name                | Default value   | Description                                                  |
|:----------------------------|:----------------|:-------------------------------------------------------------|
| S_TrackmaniaUIProperties    | ""              | The UI properties to hide. <br/> Add value to enable plugin. |

Example of a valid S_TrackmaniaUIProperties value : <br>
```
<ui_properties><round_scores visible='false'/></ui_properties>
```
