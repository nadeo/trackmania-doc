# Examples (Team competition)

Below are a few structure examples for Team competitions that you can use as a starting point for your competition.

## Single elimination bracket

A standard single elimination bracket. Below is an example of a single elimination bracket with 8 teams. You will need to manually set a seed for each team in the Teams menu.

![Single elimination with a quarterfinal of 8 teams (4 matches), a semifinal of 4 teams (2 matches), and a final](../../../img/competition-tool-bracket-example-team.png)


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
                "spotType": "competition_team",
                "seed": 1
              },
              {
                "spotType": "competition_team",
                "seed": 8
              }
            ]
          },
          {
            "spots": [
              {
                "spotType": "competition_team",
                "seed": 4
              },
              {
                "spotType": "competition_team",
                "seed": 5
              }
            ]
          },
          {
            "spots": [
              {
                "spotType": "competition_team",
                "seed": 2
              },
              {
                "spotType": "competition_team",
                "seed": 7
              }
            ]
          },
          {
            "spots": [
              {
                "spotType": "competition_team",
                "seed": 3
              },
              {
                "spotType": "competition_team",
                "seed": 6
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
                "spotType": "team_match_participant",
                "roundPosition": 0,
                "matchPosition": 0,
                "rank": 1
              },
              {
                "spotType": "team_match_participant",
                "roundPosition": 0,
                "matchPosition": 1,
                "rank": 1
              }
            ]
          },
          {
            "spots": [
              {
                "spotType": "team_match_participant",
                "roundPosition": 0,
                "matchPosition": 2,
                "rank": 1
              },
              {
                "spotType": "team_match_participant",
                "roundPosition": 0,
                "matchPosition": 3,
                "rank": 1
              }
            ]
          }
        ]
      }
    },
    {
      "name": "round 3",
      "matchGeneratorType": "spot_filler",
      "matchGeneratorData": {
        "matches": [
          {
            "spots": [
              {
                "spotType": "team_match_participant",
                "roundPosition": 1,
                "matchPosition": 0,
                "rank": 1
              },
              {
                "spotType": "team_match_participant",
                "roundPosition": 1,
                "matchPosition": 1,
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

## Round robin

A competition format where each team plays against each other at least once. Results are normally determined by a team's win-loss record. (e.g. TMGL Regular Season)

Below is an example for a 4-team round robin tournament, where each team faces each other once. You will need to manually set a seed for each team in the Teams menu.

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
                "spotType": "competition_team",
                "seed": 1
              },
              {
                "spotType": "competition_team",
                "seed": 4
              }
            ]
          },
          {
            "spots": [
              {
                "spotType": "competition_team",
                "seed": 2
              },
              {
                "spotType": "competition_team",
                "seed": 3
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
                "spotType": "competition_team",
                "seed": 1
              },
              {
                "spotType": "competition_team",
                "seed": 2
              }
            ]
          },
          {
            "spots": [
              {
                "spotType": "competition_team",
                "seed": 3
              },
              {
                "spotType": "competition_team",
                "seed": 4
              }
            ]
          }
        ]
      }
    },
    {
      "name": "round 3",
      "matchGeneratorType": "spot_filler",
      "matchGeneratorData": {
        "matches": [
          {
            "spots": [
              {
                "spotType": "competition_team",
                "seed": 1
              },
              {
                "spotType": "competition_team",
                "seed": 3
              }
            ]
          },
          {
            "spots": [
              {
                "spotType": "competition_team",
                "seed": 2
              },
              {
                "spotType": "competition_team",
                "seed": 4
              }
            ]
          }
        ]
      }
    }
  ]
}
```