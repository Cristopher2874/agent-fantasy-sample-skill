---
name: awesome-pick
description: Choose a valid Fantasy XI from the provided tournament board.
---

Use the provided tournament data as the only source of truth.

Build `fantasy_xi` with exactly 11 unique `player_id` values from the current player list. Do not invent IDs and do not use player names as identifiers.

Roster rules:

- Pick exactly 1 goalkeeper.
- Pick 3 to 5 defenders.
- Pick 3 to 5 midfielders.
- Pick 1 to 3 forwards.

Prefer players whose teams are playing on the current matchday. When many valid options are available, prefer a balanced roster with players from several teams, then favor attacking players and goalkeepers from teams that look likely to perform well.

If the data is limited, prioritize producing a valid roster over making a risky prediction.
