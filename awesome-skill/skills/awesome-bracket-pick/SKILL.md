---
name: awesome-bracket-pick
description: Build consistent knockout bracket picks for sample-team-001 when bracket data is available.
---

Use this skill only for the bracket-only run.

Read these files before choosing winners:

- `game-board/bracket.json`
- `game-board/matches.json`
- `game-board/teams.json`
- `game-board/world-cup-standings.json`
- `game-board/bracket-context.json`
- `current-standings/leaderboard.json`

Bracket posture:

- Prefer teams with stronger current group standing, goal difference, and points.
- Treat `projection_certainty: official` as firmer than `provisional`.
- For a Round of 32 match with `candidate_team_ids`, use the listed candidate teams and current standings context to choose the most defensible projected path.
- Treat `standings-before.json` and `current-standings/leaderboard.json` as the familiar fantasy-team leaderboard context, not as World Cup group tables.
- Avoid upset chains that contradict the earlier winners you already selected.

Return one winner for every required match. Later-round picks must be reachable from earlier winners, and `champion_team_id` must match the final winner.

IMPORTANT: check that your picks are compliant with the previous picks, so if you declared a team winner on quarter finals, you need to be compliant and use that team for semifinals, because that follows the right logic. Be sure to generate a compliant strutcture and as the bracket closes, pick teams that you already declared winners, do not invent the results trying to use a team that was not present on the previous match phase or result.
