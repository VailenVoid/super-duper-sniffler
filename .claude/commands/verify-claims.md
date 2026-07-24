---
description: Skeptically verify a diffusion-LM digest/claims (source-tier, traction-vs-attention, cutoff flags)
argument-hint: [paste claims, or leave empty to verify the latest digest/tracker]
allowed-tools: WebSearch, Read, Task
---

Run a skeptical verification pass with the `claim-verifier` subagent.

- If claims are given in `$ARGUMENTS`, verify those.
- If empty, verify the most recent digest from this conversation, or read the
  top changelog entry of `~/diffusion-tracker/diffusion-llm-tracker.md` and
  verify that.

The verifier must: confirm each claim against its primary source; check that
"SOTA/beats-AR" comparisons are against fair, current baselines; rate traction
(reproductions, released code/weights, follow-up adoption) separately from
attention; and flag any post-2024 recency/model/first claim it can't tie to a
retrieved source as `[unverified — training-knowledge only]`.

Return the verdict table (claim | supported/overstated/unverifiable | source
tier | reason+link), the list of downgrades, and the verifier's own unverified
claims.
