# Changes

Short log of what changed and why. Kayne's agents and Gamble Limited's agents both add lines here.

- 2026-10-30: Repo moved to the Gamble-Limited-Ltd org. Added AGENTS.md, CLAUDE.md, this file, and the on-demand Claude workflow.
- 2026-10-30: GitHub Pages now deploys only from TopTierDevelopment-Thiessen (dev). main is for prod and is pulled by the server.
- 2026-10-31: Added CI checks (scripts/ci-check.mjs).
- 2026-10-31: README rewritten for v2.23.
- 2026-10-30: Added LICENSE (PolyForm Noncommercial 1.0.0), chosen by Kayne in issue #4.
- 2026-10-31: Added the Ops workflow (start/stop/restart/status/sync of the hosted game) and its notes in AGENTS.md.
- 2026-11-01: v2.24 "Fresh Build" — the game now reads version.json on boot and, when the site's feed is newer than the running build, shows a one-tap UPDATE NOW banner that reloads through a cache-busting ?v= (fixes players stuck on stale cached copies while fixes shipped around them — the "still can't see Toronto" class of reports). Toronto itself verified on v2.23: Chicago→Toronto travel, real-OSM import (1134 roads / 118 buildings), generator fallback, walking auto-enter and shore markers all pass with zero errors.
- 2026-11-01: README updated for v2.24 — notes the boot self-update check, live play URLs, and controls re-verified against the game (dropped the not-yet-built teleport row). The same README replaced main's copy, which still described the removed v1 multiplayer game and a dead Pages URL; main's AGENTS.md drift (v2.23 / "nothing reads version.json") fixed in the same push.
- 2026-11-01: v2.25 "The Long Walk" — fixes "teleport to Chicago and no other city loads": (1) the WALK-TO pill showed the CAMERA'S distance to the next city, so a panned bird's-eye view claimed "0.9 KM" while the tycoon stood 4.7 km away and the city ahead (which streams around the tycoon) never built — the pill now shows the tycoon's true distance and flags a decoupled view ("VIEW 4.7 KM FROM YOUR TYCOON (C)"); (2) far walks died SILENTLY within seconds of setting out — the straight line from a downtown spawn to the first inter-city road vertex crosses building blocks, the walk dead-stuck-cancelled after 1.6 s — setGoal now prepends street-hop routing (road-vertex to road-vertex along clear segments) so the tycoon leaves town along the streets at full jog; (3) a walk that gives up now toasts why instead of vanishing; (4) enterWorld's teardown is guarded so a teardown bug can never silently swallow a travel.
