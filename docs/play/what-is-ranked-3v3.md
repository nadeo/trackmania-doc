# What is the Ranked 3v3 gamemode?

Trackmania offers a skill-based Ranked matchmaking mode open to all players.
Matches are played in a tweaked version of the Teams gamemode, with a points limit of 5.

You can either queue solo or with up to two other players.
When enabled, you can use voice chat to communicate with your teammates.

## The Ranked 3v3 gamemode explained

When you queue up for a Ranked 3v3 match, you will be matched with and against players from similar matchmaking ranks.
After a 30 second warmup period once all players are connected, the match will start.

Every player starts at the same time and earns points for their team based on the position they finish. The team who gets the most points wins the round.
The scoring works as follows:

| Position |  Points  |
| :------: | :------: |
|   1st    | 6 points |
|   2nd    | 5 points |
|   3rd    | 4 points |
|   4th    | 3 points |
|   5th    | 2 points |
|   6th    | 1 point  |
|   DNF    | 0 points |

The minimum amount of points a team needs to win the round, should all players finish, is 11 points.

In case a player disconnects from the match, the scoring changes a bit.
Only the best two players from each team score points and in case of a draw in points, the team with the best time in the round wins.

## Ranked map pool

Ranked 3v3 Matchmaking in Trackmania is played on the current Seasonal Campaign maps.

The map for your match will be randomly chosen out of the map pool based on the skill bracket of the lowest ranked player in the match.

The current map pool distribution is as follows:

| Skill bracket |  Map pool   |
| :-----------: | :---------: |
|    Bronze     | Maps 1 - 10 |
|    Silver     | Maps 1 - 15 |
|     Gold      | Maps 1 - 20 |
|    Master     | Maps 1 - 25 |

## Matchmaking rating

Once a team has won 5 rounds, the match ends and players will earn or lose rating points depending on the amount of points they earned for their team and whether their team won or lost.

In a regular match, where both teams are of equal skill, the point distribution is as follows:

| Winning Team position | Points gained | Losing Team position | Points lost |
| :-------------------: | :-----------: | :------------------: | :---------: |
|          1st          |      +40      |         1st          |     -20     |
|          2nd          |      +30      |         2nd          |     -30     |
|          3rd          |      +20      |         3rd          |     -40     |

The player who scored the most points in the entire match, no matter whether they are on the winning or losing side, is the Match MVP and earns bonus rating points.
The amount of bonus MVP points depends on the skill bracket the player is in and how evenly skilled the teams are. The values below assume evenly matched teams:

|  Skill bracket   | MVP bonus points |
| :--------------: | :--------------: |
|      Bronze      |       +80        |
| Silver and above |       +40        |

At the end of a matchmaking season (which runs in parallel to the campaign seasons), matchmaking ranks and ratings will be soft-reset to prevent the ratings at the top from becoming stale.

|   Before seasonal reset    |       After seasonal reset        |
| :------------------------: | :-------------------------------: |
|    Trackmaster/Master 3    |              Gold 3               |
|          Master 2          |              Gold 2               |
|          Master 1          |              Gold 1               |
|           Gold 3           | mid Silver 3 (around 1800 points) |
|           Gold 2           |             Silver 3              |
|           Gold 1           |             Silver 2              |
|          Silver 3          |             Silver 1              |
|          Silver 2          |             Bronze 3              |
| Silver 1/Bronze 3/Bronze 2 |             Bronze 2              |
|          Bronze 1          |             0 points              |
|      Inactive players      |             0 points              |

Note that inactive players are defined as players that have not played a Ranked match in the previous season.

At higher ranks, there is also an additional rank decay system. Note that you only lose points once you're out of immunity days.

|   Skill bracket   | Maximum immunity | Points change per day of inactivity |
| :---------------: | :--------------: | :---------------------------------: |
| Trackmania/Master |     10 days      |                 -20                 |
|       Gold        |     15 days      |                 -10                 |

When reaching each skill bracket, you're granted the maximum number of immunity days - you regain them by playing matches.

<hr>
Authors: [Chris92](https://twitter.com/Chris92_de)/[tooInfinite](https://twitter.com/davidbmaier)
