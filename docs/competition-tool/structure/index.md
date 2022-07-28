# Structure

To create a new competition in the admin website you can import an existing structure
or create a new one.

A structure (spot structure) defines composition of your competition. Without a
structure it is not possible to generate matches of a round.

## Create your own structure

### Rounds
At first, you must choose number of rounds.
For example a structure with two rounds: 
```json
{
  "version": 1,
  "rounds": [
    {
      "name": "round 1",
      "matchGeneratorType": "spot_filler",
      "matchGeneratorData": {
        "matches": []
      }
    },
    {
      "name": "round 2",
      "matchGeneratorType": "spot_filler",
      "matchGeneratorData": {
        "matches": []
      }
    }
  ]
}
```
Of course, you can add more rounds.

### Matches

Once, you have chosen the number of rounds and write them like the first example.
You can define number of matches per round.
For example in the round 1, we decide to add 3 matches:
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
        "matches": []
      }
    }
  ]
}
```


### Players
For each match, you must add at least one player. 
There are 4 options to add one. <br>

**Participant from a qualifier** <br>
A qualifier need to be attached to a round.<br>
`roundPosition` starts at 0 and `rank` starts at 1. (First round is at position 0).
```json
{
  "spotType": "round_challenge_participant",
  "roundPosition": 0,
  "rank": 1
}
```

**Participant from a previous round match**<br>
`roundPosition` and `matchPosition` start at 0.  (First round and first match in a round are at position 0)<br>
`rank` starts at 1.
```json
{
  "spotType": "match_participant",
  "roundPosition": 0,
  "matchPosition": 0,
  "rank": 1
}
```

**Participant with a seed**<br>
You must set the seed for each participant from the admin panel after the creation.<br>
`seed` starts at 1.
```json
{
  "spotType": "competition_participant",
  "seed": 1
}
```

**Participant from leaderboard**<br>
Based on the current competition leaderboard.<br>
`rank` starts at 1.
```json
{
  "spotType": "competition_leaderboard",
  "rank": 1
}
```

**Example**<br>
In this following example, we add two players per match. <br>
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
            "spots": [
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": "1"
              },
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": "6"
              }
            ]
          },
          {
            "spots": [
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": "2"
              },
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": "5"
              }
            ]
          },
          {
            "spots": [
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": "3"
              },
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": "4"
              }
            ]
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
            "spots": [
              {
                "spotType": "match_participant",
                "roundPosition": 0,
                "matchPosition": 0,
                "rank": 1
              },
              {
                "spotType": "match_participant",
                "roundPosition": 0,
                "matchPosition": 1,
                "rank": 1
              },
              {
                "spotType": "match_participant",
                "roundPosition": 0,
                "matchPosition": 2,
                "rank": 1
              }
            ]
          }
        ]
      }
    }
  ]
}
```
