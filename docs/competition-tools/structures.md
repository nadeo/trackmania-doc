# Spot structure

To create a new competition in the admin website you can import an existing spot structure <br>
or create a new one. <br>

## Examples

#### Bracket simple - 2 round - 3 matches - 4 players/match - with qualifier

```json
{
  "version": 1,
  "rounds": [
    {
      "name": "round 1",
      "matchGeneratorType": "spot_filler",
      "matchGeneratorData":
      {
        "matches": [
          {
            "spots": [
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": 1
              },
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": 3
              },
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": 5
              },
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": 7
              }
            ]
          },
          {
            "spots": [
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": 2
              },
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": 4
              },
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": 6
              },
              {
                "spotType": "round_challenge_participant",
                "roundPosition": 0,
                "rank": 8
              }
            ]
          }
        ]
      }
    },
    {
      "name": "round 2",
      "matchGeneratorType": "spot_filler",
      "matchGeneratorData":
      {
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
                "matchPosition": 0,
                "rank": 2
              },
              {
                "spotType": "match_participant",
                "roundPosition": 0,
                "matchPosition": 1,
                "rank": 2
              }
            ]
          }
        ]
      }
    }
  ]
}
```

#### Bracket simple - 2 round - 3 matches - 4 players/match - without qualifier
```json
{
  "version": 1,
  "rounds": [
    {
      "name": "round 1",
      "matchGeneratorType": "spot_filler",
      "matchGeneratorData":
      {
        "matches": [
          {
            "spots": [
              {
                "spotType": "competition_participant",
                "seed": 1
              },
              {
                "spotType": "competition_participant",
                "seed": 3
              },
              {
                "spotType": "competition_participant",
                "seed": 5
              },
              {
                "spotType": "competition_participant",
                "seed": 7
              }
            ]
          },
          {
            "spots": [
              {
                "spotType": "competition_participant",
                "seed": 2
              },
              {
                "spotType": "competition_participant",
                "seed": 4
              },
              {
                "spotType": "competition_participant",
                "seed": 6
              },
              {
                "spotType": "competition_participant",
                "seed": 8
              }
            ]
          }
        ]
      }
    },
    {
      "name": "round 2",
      "matchGeneratorType": "spot_filler",
      "matchGeneratorData":
      {
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
                "matchPosition": 0,
                "rank": 2
              },
              {
                "spotType": "match_participant",
                "roundPosition": 0,
                "matchPosition": 1,
                "rank": 2
              }
            ]
          }
        ]
      }
    }
  ]
}
```
