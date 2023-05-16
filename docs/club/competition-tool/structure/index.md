# Structure object

To add rounds in the Competition tool you can import a preset structure object to allow reuse of the same rounds format in other competitions. You can read more importing a structure to your Competition [in this page](../create-competition/structure-importer.md).

A **structure object** is a JSON containing rounds, matches, and player spot allocations in a Competition. The following page contains a reference of all the properties available.

## Rounds

A **round** is an object which contains an array of matches. Each round is composed of at least one match which contains an array of participants.

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

### Properties

- `name`: The name of the round (e.g. "Semifinal").
- `matchGeneratorType`: Is always `spot_filler`.
- `matchGeneratorData`:
    - `matches`: An array of [Matches](#matches) in a round. A round can have one or more matches.

## Matches

Each round will always have one or more matches. A **match** object is where you determine player placements for a specific match in a round.

```json
{
  "matches": [
    {
      "spots": [],
      "settings": {}
    }
  ]
}
```

### Properties

- `spots`: An array of [Spots](#spots) to allocate players participating in the competition into the match.
- `settings`: Additional script settings. If certain matches contains a different script settings from the ones set in [Round settings](../create-competition/rounds.md#settings), here you can script settings for that specific match.

## Spots

A **spot** is an object which determines which player is allocated to that specific spot in a match. It contains different properties depending on which `spotType` is set for that specific

### Properties

The following properties are available for all types of spot objects.

- `spotType`: determines a **spot type** (i.e. how a player is placed in a match) for that particular spot in a match.

### Solo competitions

The following spot types are available for Solo competitions.

#### Qualifier

Add a player from the qualifier leaderboard. To enable this spot type, a qualifier needs to be attached to a round.

- `spotType`: `round_challenge_participant`
- `roundPosition`: An index position (starting at `0`) of the qualifier round.
- `rank`: The rank of the player (starting at `1`).

!!! example "Example"

    ```json
    {
      "spotType": "round_challenge_participant",
      "roundPosition": 0,
      "rank": 4
    }
    ```

    _The player in 4th position in the qualifier leaderboard is added to the match._

#### Previous round

Add a player based on their placement in the previous round.

- `spotType`: `match_participant`
- `roundPosition`: The index position of the round to add the player from (starting at `0`)
- `matchPosition`: The index position of the match to add the player from (starting at `0`)
- `rank`: The rank of the player (starting at `1`).

!!! example "Example"

    ```json
    {
      "spotType": "match_participant",
      "roundPosition": 0,
      "matchPosition": 3,
      "rank": 2
    }
    ```

    _The 2nd place finisher of the fourth match of the first round is added to the match._

#### Player with a seed

Add a player based on the seed allocated to them. You will have to manually set the seed for each player from the Players page after creating your competition.

- `spotType`: `competition_participant`
- `seed`: The seed given to the player (starting at `1`).

!!! example "Example"

    ```json
    {
      "spotType": "competition_participant",
      "seed": 10
    }
    ```

    _The player with seed 10 is added to the match._

#### Leaderboard

Add a player based on their current placement in the competition leaderboard.

- `spotType`: `competition_participant`
- `rank`: The player's current position in the competition leaderboard (starting at `1`).

!!! example "Example"

    ```json
    {
      "spotType": "competition_leaderboard",
      "rank": 5
    }
    ```

    _The player at 5th position in the current competition leaderboard is added to the match._

### Team competitions

The following spot types are available for Team competitions.

#### Team with a seed

Add a team based on the seed allocated to them. You will have to manually set the seed for each team from the Teams page after creating your competition.

- `spotType`: `competition_team`
- `seed`: The seed given to the team (starting at `1`).

!!! example "Example"

    ```json
    {
      "spotType": "competition_team",
      "seed": 4
    }
    ```

    _The team with seed 4 is added to the match._

#### Team name

Add a specific team into the match.

- `spotType`: `competition_team_id`
- `competitionId`: Is always `null`.
- `teamId`: The name of the team (must be as exactly set in the Teams page).

!!! example "Example"

    ```json
    {
      "spotType": "competition_team_id",
      "competitionId": null,
      "teamId": "Team Name"
    }
    ```

    _Team "Team Name" is added to the match._

#### Previous round

Add a team based on their placement in the previous round.

- `spotType`: `team_match_participant`
- `roundPosition`: The index position of the round to add the team from (starting at `0`)
- `matchPosition`: The index position of the match to add the team from (starting at `0`)
- `rank`: The rank of the team (starting at `1`).

!!! example "Example"

    ```json
    {
      "spotType": "team_match_participant",
      "roundPosition": 0,
      "matchPosition": 1,
      "rank": 2
    }
    ```

    _The 2nd place team of the second match of the first round is added to the match._
