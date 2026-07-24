---
description: Weekly grooming of the diffusion-LM living tracker (prune, don't just append)
allowed-tools: WebSearch, Read, Write, Edit, Task
---

Groom the living doc at `~/diffusion-tracker/diffusion-llm-tracker.md`. Read
`~/diffusion-tracker/brief.md` first for the rubric and standing rules.

Do a fresh weekly scan, then MAINTAIN the doc — the point is grooming, not
appending. Run these steps:

1. **Scan.** Use the `diffusion-scout` subagent to produce this week's ranked
   digest (top 8–10). Optionally verify the top items with `claim-verifier`
   before writing anything you'd act on.
2. **Changelog.** Read the existing `## Changelog` section. Consolidate the
   trailing week's daily entries into ONE dated weekly rollup (dedupe repeats
   across days), prepend it newest-first, and keep older weekly rollups below.
3. **Moving now board.** Update statuses IN PLACE (hot / cooling / watch) based
   on this week's evidence. Demote or remove anything now stale. Add genuinely
   new live threads. Do not let a months-old item sit as "hot".
4. **State of play.** REWRITE this paragraph from scratch (≤10 lines) to reflect
   the current picture. Never append to it.
5. **Watchlist.** Move any resolved items to the "Resolved" note with their
   outcome. Add new papers-to-read / open questions surfaced this week.
6. **Anti-rot.** Every item carries a date. Tag anything not backed by a
   retrieved source `[unconfirmed]`. Prune — a pass that only adds is a failed
   pass.

Finish by updating the "Last groomed" line at the top of the doc to today's
date, and print a short summary of what changed (added / demoted / removed /
resolved) plus any "couldn't verify" items.

$ARGUMENTS
