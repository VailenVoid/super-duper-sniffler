---
description: On-demand fan-out survey of diffusion LMs (4 parallel slices → verify → merge)
argument-hint: [optional topic; defaults to full diffusion-LM landscape]
allowed-tools: WebSearch, Read, Write, Task
---

Map the current state of diffusion language models (or the topic in
`$ARGUMENTS`) by fanning out parallel subagents, then merging into ONE report.
Read `~/diffusion-tracker/brief.md` first so the shared brief (rubric, schema,
standing rules) is what every slice inherits.

## Step 1 — fan out (concurrent)
Launch **four `diffusion-slice-researcher` subagents in a single turn**, split
by subtopic (one axis, not blended). Give each the shared brief and a DISJOINT
scope, and tell each explicitly what NOT to cover:
1. **Training objectives** — score-entropy, masked/absorbing, D3PM lineage.
2. **Sampling / decoding & inference-time scaling** — remasking schedules,
   step-count reduction, guidance.
3. **Scaling & benchmark results vs. autoregressive baselines.**
4. **Applications** — code, reasoning, controllable generation.

Each returns the fixed slice schema (key findings + links, consensus vs.
contested, top-3 sources, open questions, couldn't-verify).

## Step 2 — verify
Pass the assembled findings to the `claim-verifier` subagent. Drop or downgrade
anything it rates overstated/unverifiable before it reaches the final report.

## Step 3 — merge (a real step, not concatenation)
Produce ONE report:
- **Landscape overview** where slices reference each other (e.g. "the remasking
  tricks in slice 2 are what make the scaling numbers in slice 3 land").
- **Timeline** (foundations → recent).
- **Where the subtopics disagree** — explicit contested-points section.
- **Ranked shortlist** of the ~8 developments that matter most.
- **One deduped source list** with tiers.
- **Unverified tail** — anything no subagent (or the verifier) could confirm.

Offer to save the report into `~/diffusion-tracker/` if I want it persisted.
