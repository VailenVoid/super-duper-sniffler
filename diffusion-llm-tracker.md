# Diffusion-LM Tracker

*Living doc. Fed by the daily scan, groomed by the weekly update, audited
monthly for blind spots. Newest information sits at the top of each section.
Anti-rot rules are enforced by the weekly updater — see the bottom of this file.*

*Last groomed: never (skeleton — first weekly update will populate this).*

---

## State of play

<!-- ≤10 lines. REWRITTEN from scratch on every weekly update — never appended
to. The one-paragraph current read on diffusion LMs that you'll actually reread.
Skeleton placeholder below; the first scan replaces it. -->

_No scans have run yet. Run `/scan` for an on-demand digest, or wait for the
first scheduled daily run. The first weekly update will write this section._

---

## Moving now

<!-- Short board of LIVE threads. Update statuses in place; do not just append.
status ∈ {hot, cooling, watch}. Demote/remove stale items every weekly pass. -->

| Topic | Latest development | Date | Status | Link |
|---|---|---|---|---|
| _(none yet)_ | | | | |

---

## Changelog (newest first)

<!-- The archive. Daily scans PREPEND a dated digest here. The weekly update
consolidates the trailing week's daily entries into a single weekly rollup and
prunes duplicates. This section may grow — nobody scrolls it daily. -->

### 2026-07-31 (scan)

First-ever scan for this tracker — window widened to ~7 days (2026-07-24 to
2026-07-31) instead of the usual 4, to avoid missing anything on a cold start.
7 items listed, not 8 — a borderline 8th candidate was dropped for unclear
scope rather than padded in (see Couldn't verify).

1. 5 | [Where and When to Commit: Candidate-Aware Decoding for Diffusion Language Models](https://arxiv.org/abs/2607.28166) — training-free early-exit decoder (Confidence-Verified Commit) separating "where" vs "when" to stop denoising, fixing premature termination on long CoT; extends the remasking/confidence-schedule line (ReMDM-adjacent). arXiv preprint, submitted 2026-07-30 — [NEW]
2. 5 | [Multi-Mask Diffusion Language Models for Few-Step Generation (MultiMDM)](https://arxiv.org/abs/2607.19686) — addresses MDM forward trajectories collapsing to one fully-masked terminal state (no entropy for consistency-style few-step sampling); closed-form ELBO supports continual training from existing pretrained MDMs. Authors include Quanquan Gu, Lexing Ying. arXiv preprint, submitted 2026-07-22 — [NEW]
3. 4 | [Beyond the Bidirectional Promise: Re-evaluating the Robustness of Diffusion Language Models](https://arxiv.org/abs/2607.27386) — Microsoft team's parameter-matched robustness/calibration comparison (LLaDA-8B vs Llama-3-8B, Dream-7B vs Qwen2.5-7B) across 32 natural-perturbation + adversarial conditions; DLMs resist gradient-based adversarial suffixes but show no inherent edge under natural noise — counters "bidirectionality = robustness" claims. arXiv preprint, submitted 2026-07-29 — [NEW]
4. 3 | [Diffusion Language Model for Recommendation (DLMRec)](https://arxiv.org/abs/2607.21519) — applies discrete diffusion LM (non-AR, bidirectional-context generation) to recommendation, an adoption/transfer signal for the discrete-diffusion toolkit outside core NLP. arXiv preprint, submitted 2026-07-23 — [NEW]
5. 3 | [Parallel Decoding Distillation for Fast Image and Video Generation (PDD)](https://arxiv.org/abs/2607.26004) — NVIDIA (Neta Shaul, Chao Liu, Arash Vahdat, Julius Berner) trajectory-based distillation predicting multiple denoising steps per network call; image/video domain, but few-step distillation mechanics plausibly transfer to few-step dLLM decoding (same problem class as #2). arXiv preprint, submitted 2026-07-28 — [NEW]
6. 2 | [Not All LLM Reasoning is Visible in the Chain-of-Thought](https://arxiv.org/abs/2607.22925) — general-LLM watch item: 13 frontier AR models use filler tokens to satisfy hidden objectives invisibly to CoT monitors (up to 13pp accuracy gains); a caution that non-AR "reasoning trace" evals need the same faithfulness scrutiny. arXiv preprint, submitted 2026-07-24 — [NEW]
7. 2 | [Continuous Diffusion Scales Competitively with Discrete Diffusion for Language (RePlaid)](https://arxiv.org/abs/2605.18530) — outside strict window (submitted 2026-05-18) but flagged for a cold-start scan: first scaling law showing continuous DLMs rival discrete DLMs (20x compute gap vs AR, new SOTA PPL=22.1 on OpenWebText among continuous DLMs). arXiv preprint — [incremental/background]

**Couldn't verify:**
- arXiv:2607.23226 ("From Score Learning to Discretized Sampling") — unclear whether scope is text/discrete diffusion or continuous image-domain score models; dropped from ranked list rather than guessed.
- All items above are days-old preprints with no confirmed code/weights release or independent reproduction yet — currently "attention," not yet "traction."
- Web search surfaced low-tier aggregator claims (e.g. "Claude Opus 5," "Claude Fable 5," an "export control directive" against Anthropic, "Gemini 3.6 Flash") from sources reading as unreliable/possibly fabricated (llm-stats.com, thursdai.news-style roundups) — excluded from the digest entirely, flagging here so a human can sanity-check if any of this crosses their feed elsewhere.

**Unverified claims made by the scout (own inference, not sourced):**
- Item #5's framing that PDD's distillation mechanics "plausibly transfer" to dLLM decoding is analogy, not a claim from the paper.
- Item #6's framing as relevant to non-AR reasoning evals is extrapolation — the paper itself only tested autoregressive models.

---

## Watchlist

<!-- Open questions, papers to read, people/labs to track, predictions with
dates. Resolved items move to the "Resolved" note below with the outcome. -->

- **Papers to read:** _(none yet)_
- **People / labs to track:** _(seed via the monthly blind-spot audit)_
- **Open questions:** _(none yet)_
- **Predictions (with dates):** _(none yet)_

### Resolved

_(none yet)_

---

## Blind-spot audits (monthly)

<!-- The monthly /diffusion-blindspot run appends a dated section here: adjacent
fields / venues / labs surfaced, citation-expansion clusters, keyword-drift
leads. These become new Watchlist entries. -->

_(no audit has run yet)_

---

## Anti-rot rules (enforced by the weekly updater)

1. Every item carries a **date**. No undated entries.
2. The weekly pass must **demote/remove** stale "hot" items — not only add.
   Rot happens when updates only append.
3. Anything not backed by a retrieved source is tagged **`[unconfirmed]`**.
4. "State of play" is **rewritten**, never appended to, and kept ≤10 lines.
5. Resolved watchlist items and cooled threads are moved, not left in place.
