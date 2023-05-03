# Structure

To create a new competition in the admin website you can import an existing structure or create a new one.

A structure (spot structure) defines composition of your competition.

## Create your own structure

### Rounds
Round is an object which contains an array of matches. 
Each round is composed of at least one match which contains an array of participants.
```json
{
  "version": 1,
  "rounds": [
    {
      "name": "round 1",
      "matchGeneratorType": "spot_filler",
      "matchGeneratorData": {
        "matches": [
          {
            "spots": []
          },
          {
            "spots": []
          }
        ]
      }
    },
    {
      "name": "round 2",
      "matchGeneratorType": "spot_filler",
      "matchGeneratorData": {
        "matches": [
          {
            "spots": []
          }
        ]
      }
    }
  ]
}
```
In this example, there are two matches in round 1 and one match in round 2.

### Players
Add participants in each match.
There are 4 options to add one.

####Participant from a qualifier <br>
A qualifier need to be attached to a round.<br>
First round is at position 0 and `rank` starts at 1.

```json
{
  "spotType": "round_challenge_participant",
  "roundPosition": 0,
  "rank": 1
}
```
_Participant is added from the qualifier of the round 1 at rank 1._

####Participant from a previous round match<br>
First round and first match in a round are at position 0<br>
`rank` starts at 1.

```json
{
  "spotType": "match_participant",
  "roundPosition": 0,
  "matchPosition": 3,
  "rank": 2
}
```
_Participant is added from match 4 of round 1 at rank 2._

####Participant with a seed<br>
Set the seed for each participant from the admin panel after the creation.<br>
`seed` starts at 1.
```json
{
  "spotType": "competition_participant",
  "seed": 10
}
```
_Participant is added from the competition participants at seed 10._

####Participant from leaderboard<br>
Participant is added from X rank in the current competition leaderboard<br>
`rank` starts at 1.
```json
{
  "spotType": "competition_leaderboard",
  "rank": 5
}
```
_Participant is added from the current leaderboard at rank 5._

### Teams
For competition with teams, add the participating teams for each match.
There are 3 options available.

#### Team with a seed
Set the seed for each team from the admin panel after the creation.<br>
`seed` starts at 1.
```json
{
  "spotType": "competition_team",
  "seed": 4
}
```
_Participant is added from the team with seed 4._

#### Team name
```json
{
  "competitionId": null,
  "teamId": "Team Name",
  "spotType": "competition_team_id"
}
```
_Team "Team Name" is added to the participants list._

#### Team from a previous round match
First round and first match in a round are at position 0<br>
`rank` starts at 1.
```json
{
  "roundPosition": 0,
  "matchPosition": 1,
  "rank": 2,
  "spotType": "team_match_participant"
}
```
_Participant is added from the team in match 2 of round 1 at rank 2._

####See a complete example [here](01-example.md)
