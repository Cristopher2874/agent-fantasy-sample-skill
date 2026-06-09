---
name: awesome-pick
description: Choose a valid Fantasy XI from the provided tournament board using a specific web-search condition tree for player selection, including source-backed search details for the run.
---

Use the provided tournament data as the source of truth for eligible players, `player_id` values, positions, teams, matches, and roster validity.

Before choosing the roster, perform fresh web research for the current run. Use the research to classify each current matchday match into a match environment, then select player types from that classification. Never use web research to invent players, teams, IDs, positions, or matches that are not present in the tournament data.

Web-search teaching pattern:

- Run at least one web search before selecting the 11 players.
- Search for the specific condition: current weather and match tempo/scoring environment for each current matchday venue or fixture. Example search topics: "`TEAM A TEAM B weather forecast venue`", "`TEAM A TEAM B expected goals odds`", "`TEAM A TEAM B lineup injury news`".
- Prefer current weather, official team news, league sources, reputable sports news, or market/odds sources when available.
- Classify each researched match using this condition tree:
  - Condition A, defensive environment: heavy rain, strong wind, poor pitch, very cold/hostile conditions, low-goal market, or multiple attacking absences. Prefer goalkeepers and defenders from stronger teams, defensive midfielders with steady minutes, and set-piece takers.
  - Condition B, attacking environment: clear weather, good pitch, high-goal market, weak defenses, or attacking starters confirmed. Prefer forwards, attacking midfielders, wingers, penalty takers, and fullbacks with crossing/assist upside.
  - Condition C, uncertainty: conflicting reports, missing lineup news, or weak sources. Prefer safe starters, balanced positions, and players whose teams are confirmed to play on the current matchday.
- Capture the search details in the final answer, including the query or topic, source links, publication or access dates when available, the A/B/C classification, and how that classification changed the roster.

Build `fantasy_xi` with exactly 11 unique `player_id` values from the current player list. Do not invent IDs and do not use player names as identifiers.

Roster rules:

- Pick exactly 1 goalkeeper.
- Pick 3 to 5 defenders.
- Pick 3 to 5 midfielders.
- Pick 1 to 3 forwards.

Prefer players whose teams are playing on the current matchday. When many valid options are available, prefer a balanced roster with players from several teams, then favor attacking players and goalkeepers from teams that look likely to perform well.

Selection workflow:

1. Read the tournament board and identify all eligible players, positions, teams, and current matchday matches.
2. Perform the required web research for weather and match tempo/scoring conditions.
3. Map research findings back to valid `player_id` values from the board.
4. Build a valid 11-player roster using the roster rules.
5. Include `web_search_details` or an equivalent research section in the response so the run shows the searched condition, the A/B/C classification, and why the selected player types match it.

If web search is unavailable or fails, state that blocker clearly, then still produce a valid roster from the provided board. If the data is limited, prioritize producing a valid roster over making unsupported predictions.
