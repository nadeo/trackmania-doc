##Example

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

+ Round 1 - participants are added from the qualifier which is attached to this round
  + Match 1
    + Participant of qualifier at rank 1 
    + Participant of qualifier at rank 6 
  + Match 2
    + Participant of qualifier at rank 2
    + Participant of qualifier at rank 5
  + Match 2
    + Participant of qualifier at rank 3
    + Participant of qualifier at rank 4


+ Round 2 - participants are added from the previous round (round 1)
  + Match 1
    + Participant of the round 1 and match 1 at rank 1
    + Participant of the round 1 and match 2 at rank 1
    + Participant of the round 1 and match 3 at rank 1
