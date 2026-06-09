---
name: awesome-risk-play
description: Choose a required green or red fantasy risk play for the current matchday using a specific web-search condition tree and source-backed run details.
---

# Risk claim always present

Always return one risk play for the current run. Choose it from the risk plays available for one of the current matchday matches. Do not skip the risk play.

Before choosing the risk play, perform a separate web search from the Fantasy XI player research. Use current public information to classify the match environment, then choose green or red from that classification.

Web-search teaching pattern:

- Run at least one web search specifically for the risk play.
- Search for the current condition: weather and match tempo/scoring environment for one current matchday fixture. Example search topics: "`TEAM A TEAM B weather forecast venue`", "`TEAM A TEAM B expected goals odds`", "`TEAM A TEAM B injury lineup news`".
- Prefer current weather, official team news, league sources, reputable sports news, or market/odds sources when available.
- Classify the researched fixture using this condition tree:
  - Condition A, cautious match: heavy rain, strong wind, poor pitch, low-goal market, missing attackers, or both teams likely to start conservatively. Choose a green risk play. If `no_goal_first_10` is available, prefer it.
  - Condition B, volatile match: clear weather, good pitch, high-goal market, weak defenses, attacking starters confirmed, derby/tension signals, or news suggesting cards/chaos. Choose a red risk play that best matches the available risk list.
  - Condition C, unclear evidence: conflicting reports, weak sources, or no strong condition. Choose the safest available green risk play.
- Capture the search details in the final answer, including the query or topic, source links, publication or access dates when available, the A/B/C classification, and how that classification determined green or red.

Risk selection rules:

- Pick a green risk for Condition A or Condition C.
- Pick a red risk for Condition B.
- If `no_goal_first_10` is available under Condition A or C, it is the preferred green default.
- If the board exposes risk IDs, return the exact risk ID. If it only exposes names/categories, return the category and claim name exactly as provided.
- Never invent a risk play that is not present in the current matchday data.

If web search is unavailable or fails, state that blocker clearly and still return one risk play. In that fallback case, prefer the safest available green risk play, especially `no_goal_first_10` when present.
