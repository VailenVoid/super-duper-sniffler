# Diffusion-LM Field-Monitoring System

A small system of agents, slash commands, a living doc, and cloud schedules that
keeps you current on diffusion language models and their neighbors. Built from
the field-monitoring playbook. Everything routes "what's newest" claims through
web search — never through model memory.

## The four moving parts

| Part | How it shows up here |
|---|---|
| Breadth now | fan-out subagents (`/diffusion-state-of-field`) |
| Breadth over time | 3 cloud schedules (daily / weekly / monthly) |
| Persistence | `diffusion-llm-tracker.md` (this folder) |
| Trust | `claim-verifier` + the standing rules in `brief.md` |

## Files in this folder

- **`brief.md`** — the shared brief: relevance rubric, output contract, standing
  quality rules. Every agent reads it first. Edit this to change what "matters."
- **`diffusion-llm-tracker.md`** — the living doc. State of play, moving-now
  board, changelog, watchlist, blind-spot audits.
- **`README.md`** — this file.

## Agents (`~/.claude/agents/`)

- **`diffusion-scout`** — daily scanner. Ranks recent diffusion-LM work against
  the rubric. (Backbone.)
- **`claim-verifier`** — skeptical reviewer. Verifies claims, tiers sources,
  separates traction from attention, flags cutoff-only claims.
- **`blindspot-scout`** — red-team against your information diet: citation
  expansion, cross-domain keyword drift, unwatched venues/labs.
- **`diffusion-slice-researcher`** — one disjoint slice of a fan-out survey;
  returns the uniform schema so the merge is mechanical.
- **`paper-scout`** — general-purpose topic literature scan (pre-existing).

## Commands (`~/.claude/commands/`)

| Command | What it does | Section |
|---|---|---|
| `/scan [topic]` | Daily ranked digest via `diffusion-scout` | §1 |
| `/diffusion-tracker-update` | Weekly grooming: rewrite state-of-play, refresh board, consolidate + prune changelog, tag unconfirmed | §4 |
| `/diffusion-blindspot` | Monthly red-team audit → appends to tracker | §3 |
| `/diffusion-state-of-field [topic]` | On-demand fan-out survey (4 slices → verify → merge into one report) | §2 |
| `/verify-claims` | Run the skeptical verifier over a pasted/last digest | §5 |

## Cloud schedules (all Europe/Sofia)

- **Daily 07:00** — run the scan; prepend a dated digest to the changelog.
- **Weekly Mon 07:00** — full tracker grooming with pruning.
- **Monthly 1st 07:00** — blind-spot + citation-expansion audit.

Manage them with the `/schedule` skill (list / edit / run-now / delete).

## Fan-out synthesis is on-demand, not scheduled

`/diffusion-state-of-field` is a powerful "state of X" deep dive — run it when
you actually need one, not on a timer.

## Note on the connector-backed dashboard (architecture B)

The playbook's live HTML dashboard needs MCP connectors (Notion / Slack /
Scholar Gateway / PubMed / bioRxiv) authorized in your claude.ai connector
settings. Until then this system uses **architecture A**: a scheduled scan that
writes this Markdown doc, which works with no connectors. Once connectors are
authorized, a connector-backed dashboard can be added on top.
