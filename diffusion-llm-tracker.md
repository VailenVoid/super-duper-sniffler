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

### 2026-08-20 (scan)

Window: 2026-08-17 to 2026-08-20 (since the 2026-08-17 scan). Genuinely quiet
for the strict Aug 17–20 window itself — no diffusion-LM item could be
confirmed with a search-verified submission date inside those four days (the
closest hit, a v2 revision of "x-Prediction Flow," was originally submitted
2026-06-27 and only got a same-content revision on 2026-08-17 — not a new
result, not ranked). What did surface is three solid items from just before
the window (Aug 12–14) that both this scan and the 2026-08-13/2026-08-17
scans' windows should have caught but didn't — same search-index-lag pattern
flagged in prior entries. 3 items, not padded to 8 — per the rubric, a short
honest list beats padding.

1. 5 | [Ripple-Pivot Search: Active Parallel Decoding for Diffusion Large Language Models](https://arxiv.org/abs/2608.11742) — training-free decoding method that identifies mid-entropy "pivot" positions whose early commitment triggers a measurable ripple-effect drop in uncertainty across remaining masked positions, then picks the pivot's token via lookahead evaluation to maximize downstream parallel-unmask benefit; a genuine new mechanism for the core "cut sampling steps while preserving quality" bucket, distinct from confidence-threshold approaches already in the tracker's decoding sub-thread — arXiv preprint, confirmed submitted 2026-08-12, no code found; missed by the 2026-08-13 scan's stated window (Aug 10–13) — [NEW, backfill/gap-flag]
2. 4 | [DeMTS: Denoising Trajectories as Multivariate Time Series for Hallucination Detection in Diffusion Language Models](https://arxiv.org/abs/2608.14632) — argues prior D-LLM hallucination detectors compress the denoising uncertainty trajectory along either the token or the step axis and lose the 2-D token-step structure (inconsistent convergence, cross-token fault propagation); models the full trajectory as a multivariate time series over learnable latents instead — directly useful for anyone building trust/calibration tooling around iterative denoising, adjacent to the tracker's confidence-remasking thread — arXiv preprint, no code found; date conflict (see Couldn't verify) — [NEW, backfill]
3. 3 | [Discrete Diffusion Language Models Are Training-Free Multi-Label Classifiers](https://arxiv.org/abs/2608.14649) — dLLM-SetScore: a training-free multi-label text classifier built from LLaDA-8B/Dream-7B by comparing yes/no answer-token probabilities at one masked position per candidate label, beating BART-MNLI/DeBERTa-NLI/SetFit/supervised baselines on 6 datasets with only a 200-example validation slice for threshold tuning; adoption/transfer signal for the discrete-diffusion toolkit outside core generation, accepted to SIAM SDM 2026 — **arXiv preprint + code** ([github.com/misterpawan/multilabel-classification-dllm-paper](https://github.com/misterpawan/multilabel-classification-dllm-paper.git)), genuine traction not just attention; date conflict (see Couldn't verify) — [NEW, backfill]

**Couldn't verify:**
- Submission-date conflicts on items 2–3: one search summary reported DeMTS as "submitted July 24, 2026" and the multi-label classifier as "submitted July 30, 2026," both inconsistent with their 2608.146xx arXiv ID prefixes (which, given the month's sequential numbering, imply ~Aug 14 — consistent with 2608.14430, independently confirmed as Aug 14 for an unrelated RL-for-diffusion paper). This is the same date-extraction anomaly flagged in the 2026-08-17 and 2026-08-13 entries (DiffusionGemma, CORA-Diff, Diffuse to Compress) — needs a direct arxiv.org abstract-page check, not just search-summary text.
- Scope of ["Designing Reinforcement Learning for Diffusion Models: A Unified Path-Space View"](https://arxiv.org/abs/2608.14430) (confirmed submitted 2026-08-14) — unifies reverse-trajectory and forward-matching RL losses for diffusion models under one path-space principle, but search results gave no indication whether it targets text/language diffusion specifically or is scoped to image/general diffusion (references DiffusionNFT, typically an image-domain method); excluded from the ranked list rather than guessed — worth a direct check next cycle given RL-for-diffusion-LM is squarely core if it applies.
- Code/weight release status for Ripple-Pivot Search (2608.11742) and DeMTS (2608.14632) — no GitHub links surfaced for either; treat as arXiv-preprint-only ("attention," not yet "traction").

**Unverified claims made by the scout (own inference, not sourced):**
- Framing items 1–3 as "missed by every prior scan" is inferred from their absence in the tracker's changelog text combined with their submission dates falling inside or just before previously-stated scan windows — plausible but not provably a search failure versus deliberate exclusion by those prior runs (same caveat raised in the 2026-08-17 and 2026-08-13 entries).
- The characterization of this window as "genuinely quiet" for the strict Aug 17–20 range is the scout's own comparative judgment across ~30 queries this run, not a sourced claim — cannot rule out search-index lag on the very newest arXiv IDs.
- Excluding general-LLM-news items surfaced this run (GLM-5.3, Gemini 3.7 Flash releases per low-tier aggregator sites like llm-stats.com/aireleasetracker.com) as non-field-shifting for diffusion-LM research is a judgment call, not a sourced fact — the releases themselves trace to aggregator pages of uncertain reliability, not primary sources, so they weren't verified independently either.
- Excluding VibeVoice (a next-token-diffusion speech-synthesis system reportedly surfaced on HF trending ~Aug 18) as out-of-scope (speech domain, not core text diffusion-LM) is the scout's own relevance judgment.

---

### 2026-08-17 (scan)

Window: 2026-08-13 to 2026-08-17 (since the 2026-08-13 scan). Genuinely thin
for the strict Aug 13–17 window — after ~30 targeted queries (arXiv ID-range
probing across 2608.08xxx–2608.17xxx, cs.CL/cs.LG/cs.AI keyword search, HF
Daily Papers, alphaXiv), only one item has a search-confirmed submission date
strictly inside the window; the other three are backfill — legitimate misses
from before Aug 13 that surfaced only on this pass. Not padded to 8 — 4 items,
per the rubric a short honest list beats padding.

1. 5 | [The data geometry of masking diffusion: Certified-optimal schedules via unmasking growth complexity](https://arxiv.org/abs/2608.13520) — Martin J. Wainwright; introduces "unmasking growth complexity" (UGC), a path-resolved data-geometry measure whose local increments directly bound KL discretization error, unifying Bernoulli-subset and fixed-cardinality unmasking schemes and yielding certified-optimal single-/multi-block schedules (provably within a constant factor of the oracle); a theory-grade companion to the tracker's remasking-schedule sub-thread — arXiv preprint, submitted 2026-08-13 (confirmed), no code found — [NEW]
2. 4 | [Commitment Before Realization: When Classifier-Free Guidance Becomes Unnecessary in Masked Diffusion Language Models](https://arxiv.org/abs/2608.08082) — defines a "commitment horizon" per prompt: the earliest point at which switching off CFG for the rest of decoding is noninferior to full CFG; shows CFG benefit is highly prompt-specific and often front-loaded, directly actionable for cutting guidance compute without a quality hit — arXiv preprint, submitted 2026-08-08, missed by every prior scan back to 2026-08-10 — [NEW, backfill/gap-flag]
3. 4 | [CORA-Diff: Confidence-Oriented Residual Acceptance for Efficient Diffusion Language Model Inference](https://arxiv.org/abs/2608.11235) — training-free confidence-and-persistence gating that only intervenes on positions a base transfer rule leaves unresolved; reports 2.70x/3.32x speedups over EOS-aware dense decoding on GSM8K/HumanEval (up to 13.14x under a fixed-horizon mechanism-isolation protocol), transfers to Dream without retuning (3.18–3.53x) — genuine efficiency-trick contribution in the core "cut sampling steps" bucket — arXiv preprint, no code found, submission date conflicts across search summaries (see Couldn't verify) — [NEW, backfill]
4. 3 | [Diffuse to Compress: Leveraging Diffusion LMs for Lossless Compression](https://arxiv.org/abs/2608.11249) — first use of DLMs (rather than AR LLMs) as the probability model backing a neural lossless text/code compressor, targeting the throughput bottleneck that has kept LLM-based compression impractical; an adoption/transfer signal for the discrete-diffusion toolkit outside core NLP generation — arXiv preprint (Angelo Nardone, Paolo Ferragina), no code found, submission date conflicts across search summaries (see Couldn't verify) — [NEW, backfill]

**Situational awareness (not scored/ranked):** two NeurIPS 2026 workshops dedicated to non-AR/diffusion generation now have confirmed listings via the [NeurIPS 2026 workshops announcement](https://blog.neurips.cc/2026/08/10/announcing-the-neurips-2026-workshops/) (Aug 10, 2026): **DiffuLM** ([site](https://7amin.github.io/diffulm-neurips2026/)) and **BeNTo: Beyond Next Token Prediction** ([site](https://bento-neurips.github.io/)), both with an Aug 29 submission deadline — expect a paper wave in the next 1–2 cycles as authors rush the deadline.

**Couldn't verify:**
- Submission-date conflicts on items 3–4 above: for CORA-Diff (2608.11235) one search summary reported "submitted July 31, 2026," and for Diffuse to Compress (2608.11249) one summary reported "submitted August 4, 2026" — both inconsistent with their arXiv ID prefixes (11xxx implies roughly Aug 11 given the month's sequential numbering, consistent with 2608.08082 confirmed as Aug 8 and 2608.13520 confirmed as Aug 13). Same date-extraction anomaly the 2026-08-13 entry flagged for DiffusionGemma — needs a direct arxiv.org abstract-page check, not just search-summary text.
- A paper referenced in search snippets as "Escaping Confidence Trap: Evolutionary Decoding for Mathematical Reasoning in Diffusion LLMs" (authors reportedly incl. Zhenhong Sun, Hanqing Zhao, Yatao Bian, Dacheng Tao) could not be pinned to a real arXiv ID — a direct ID lookup (2608.00610) resolved to an unrelated paper ("Slides2MindMap"), meaning the search tool likely hallucinated or misattributed that ID. Excluded from the ranked list entirely rather than guessed; worth a direct author/title search next cycle.
- Could not confirm code/weight release for any of the four ranked items above — all currently arXiv-preprint-only ("attention," not yet "traction").

**Unverified claims made by the scout (own inference, not sourced):**
- Inferring CORA-Diff's and Diffuse to Compress's actual submission dates from their arXiv ID numeric position within the August 2026 sequence (rather than an explicitly confirmed date string) is the scout's own extrapolation, not a directly retrieved fact — flagged above as a live date conflict, not resolved.
- Framing 2608.08082 and 2608.11235 as "missed by every prior scan" is inferred from their absence in the tracker's changelog text combined with their submission dates falling inside previously-stated scan windows — plausible but not provably a search failure versus deliberate exclusion by those prior runs (same caveat the 2026-08-13 entry raised about DiffusionGemma).
- The characterization of the window as "genuinely thin" / repeating a search-index-lag pattern from prior cycles is the scout's own comparative judgment across changelog entries, not a sourced claim.

---

### 2026-08-13 (scan)

Window: 2026-08-10 to 2026-08-13 (since the 2026-08-10 scan), plus a backfill
of 2026-08-06–2026-08-10 items the prior scan's window should have caught but
didn't, plus one significant older item (2026-07-31) that appears to have
slipped through every prior cycle. Genuinely thin for the strict Aug 10–13
window — only one clearly in-window item surfaced despite ~15 targeted
queries (arXiv ID-range probing, cs.CL/cs.LG date-string search, HF Daily
Papers). Not padded to 8 — 5 items, per the rubric a short honest list beats
padding.

1. 5 | [DiffusionGemma Technical Report](https://arxiv.org/abs/2608.00146) — Google DeepMind's 26B-total/3.8B-active MoE discrete-diffusion LM, Apache-2.0 open weights, native [vLLM support](https://vllm.ai/blog/2026-06-10-diffusion-gemma), ~1,000–1,500 tok/s on one H100 (~4x faster than AR Gemma 4 per Google's own report); strongest traction signal (real weights + serving-framework adoption, not just a demo) this tracker has logged to date, yet it does not appear in any prior scan entry back to 2026-07-31 — a real gap, not a new find — [NEW, backfill/gap-flag]
2. 5 | [Simplex Relaxation for Discrete Diffusion (Simplax)](https://arxiv.org/abs/2608.10615) — exact Dirichlet–categorical augmentation for uniform discrete diffusion that preserves the categorical marginal while yielding a tractable Rao–Blackwellized reverse-bridge objective and stochastic reverse sampler; a genuine new-training-objective contribution, in-window (submitted 2026-08-11), arXiv preprint, no code confirmed — [NEW]
3. 4 | [Archer: Adaptive Reuse of Cached Hidden States for Efficient Rollback in Diffusion Language Models](https://arxiv.org/abs/2608.08086) — reversibility-aligned cache boundary + decoder-margin condition for reusing prompt hidden states across denoising steps; reports 2.57x mean speedup with improved Pass@1; **code released** ([github.com/Hxnng/Archer](https://github.com/Hxnng/Archer)) — genuine efficiency traction, not just attention; submitted 2026-08-08, missed by the 2026-08-10 scan's window — [NEW, backfill]
4. 4 | [Unsure but Certain: Uncovering the Representation-Confidence Gap in Diffusion Language Models](https://arxiv.org/abs/2608.08791) — shows dLLMs internally detect their own errors accurately but externally reported confidence stays near-maximal regardless, and this ranking failure resists score recalibration and matched-noise training; directly bears on confidence-based remasking/unmasking-schedule design (the tracker's core sub-thread) — arXiv preprint, submitted 2026-08-09, missed by the 2026-08-10 scan's window — [NEW, backfill]
5. 3 | [Diffusion LLMs as Targets and Adversaries: Mechanistic Safety Exploits](https://arxiv.org/abs/2608.07430) — shows safety alignment in DLLMs is mechanistically sparse and transferable across architectures, exposing new attack surfaces specific to iterative parallel denoising; watch/high-tier since it's evals/security rather than core sampling-schedule work, but relevant to anyone deploying a dLLM — arXiv preprint, submitted 2026-08-07, missed by the 2026-08-10 scan's window — [NEW, backfill]

**Couldn't verify:**
- DiffusionGemma's own reported speed/quality numbers (4x, ~1,000–1,500 tok/s) trace only to Google's technical report and Google-adjacent coverage (vLLM blog, Google dev blog) — no independent third-party benchmark or reproduction found yet.
- The DiffusionGemma release-date discrepancy itself: multiple outlets (MarkTechPost, GIGAZINE, vLLM blog) date the public model release "June 10, 2026," while the arXiv technical report (2608.00146) shows a v1 timestamp of "Friday, 31 Jul 2026" — i.e., weights/blog reportedly predate the technical writeup by ~7 weeks; both dates are search-sourced but conflict, flagging for human sanity-check.
- Could not confirm code/weight release for Simplex Relaxation (2608.10615) or Unsure but Certain (2608.08791) — no GitHub links surfaced for either; treat as arXiv-preprint-only.
- Could not find any item with a confirmed submission date of 2026-08-12 or 2026-08-13 (today) specifically — likely search-index lag on the very newest arXiv IDs rather than a genuinely empty two days; worth a direct `arxiv.org/list/cs.CL/recent` check next cycle instead of relying on search engines alone.

**Unverified claims made by the scout (own inference, not sourced):**
- Framing DiffusionGemma as having been "missed by every prior scan" is inferred from its absence in the tracker's changelog text, not a confirmed statement that prior scans searched for it and failed — it's possible it simply fell outside each cycle's strict date window every time by construction.
- The characterization of DiffusionGemma as "the strongest traction signal this tracker has logged to date" is the scout's own comparative judgment across the changelog, not a sourced claim.
- Scoring items 3–5 as "backfill" (i.e., that the 2026-08-10 scan's search pass should have caught them but didn't) is an inference from their arXiv IDs falling inside that scan's stated window combined with their absence from its entry — plausible but not something that can be proven as a search miss versus a deliberate exclusion by that prior run.

---

### 2026-08-10 (scan)

Window: 2026-08-06 to 2026-08-10 (since the 2026-08-06 scan). Quiet cycle:
extensive arXiv (cs.CL/cs.LG/cs.AI) and Hugging Face Daily Papers searches
turned up only one clearly in-window core item, plus one watch-tier item
from just before the window that the prior scan missed. AURORA-LM
(arXiv:2608.02602) resurfaced in this search pass but is NOT re-listed — it
was already logged in the 2026-08-06 entry above. 2 items, not padded to
8 — per the rubric, a short honest list beats padding.

1. 5 | [Answer First, Reason Later: Commitment Order in Diffusion LLMs](https://arxiv.org/abs/2608.05687) — logs per-token commitment during LLaDA-8B decoding on GSM8K and shows unconstrained any-order decoding freezes the final answer at 15–24% of the trajectory, collapsing to answer-only outputs on up to 90% of problems as canvas grows; directly bears on remasking/scheduling design for reasoning-capable diffusion LMs, and is the latest entry in a fast-moving token-commitment-order sub-thread (see prior entries: "The Path Matters" 2605.24697, "Don't Commit Alone" 2607.04469, "Neither Parallel Nor Sequential" 2606.14620, "Where and When to Commit" 2607.28166). arXiv preprint, submitted 2026-08-06, no code/weights found — [NEW]
2. 2 | [Test-Time Scaling in Reasoning LLMs: Inference Regimes, Evaluation, and Reproducibility](https://arxiv.org/abs/2608.04001) — large empirical/methodology study of test-time-compute regimes (deliberation, sampling+voting, search) for autoregressive reasoning LLMs; watch-tier because its evaluation/reproducibility framework plausibly transfers to how diffusion-LM inference-time-scaling claims should be benchmarked. arXiv preprint, submitted 2026-08-04 (missed by the 2026-08-06 scan's window) — [NEW]

**Also noted (not scored/ranked, predates window, for situational awareness only):**
- A first NeurIPS 2026 workshop dedicated to diffusion language models ("DiffuLM") has a paper deadline of 2026-08-29 — [workshop site](https://7amin.github.io/diffulm-neurips2026/) — expect a submission wave in the next 2–3 weeks.

**Couldn't verify:**
- No GitHub code/weights link found for "Answer First, Reason Later" (2608.05687) — traction unconfirmed, treat as attention-only for now.
- Could not confirm via search whether any diffusion-LM-specific paper was newly featured on Hugging Face's Daily Papers trending list within this window — results returned only general/adjacent trending topics (long-horizon agents, video diffusion), not a diffusion-LM-specific trending entry.

**Unverified claims made by the scout (own inference, not sourced):**
- The exact arXiv submission timestamps (Aug 6, Aug 4) for the two items above are as reported by search-tool summarization of arXiv metadata, not independently re-verified against the raw arXiv abstract page HTML.
- Framing the Test-Time Scaling paper's eval framework as "plausibly transferable" to diffusion-LM benchmarking is the scout's own relevance judgment, not a stated claim in the paper.

---

### 2026-08-06 (scan)

Window: 2026-08-02 to 2026-08-06 (since the 2026-08-03 scan). Active but
incremental: five new arXiv preprints, all with IDs implying ~Aug 3, 2026
submission, clustered on decoding/sampling/inference-efficiency for diffusion
LMs (speculative-style draft-refine, MoE compute allocation, diversity
guidance). None rises to a new-training-objective or scaling-law-level
result. No code releases found for any item. No follow-up on the four items
logged in the 2026-08-03 entry (Mean-to-Score, UNIFUSION, Explorative
Modeling, NonAR-LM workshop) — not re-listed. 5 items, not padded to 8 — per
the rubric, a short honest list beats padding.

1. 5 | [AURORA-LM: Autoencoding Unified Representation for Continuous-Latent Diffusion LM](https://arxiv.org/abs/2608.02602) — query-based encoder-decoder + block-causal diffusion transformer trained via flow matching; direct lineage to continuous-latent (vs. discrete) diffusion LM approaches. arXiv preprint, submitted ~2026-08-03 — [NEW]
2. 5 | [Speculative Correction: Draft-then-Refine Decoding for Diffusion LMs](https://arxiv.org/abs/2608.02625) — plug-and-play draft-then-bidirectionally-refine inference pattern on LLaDA2.1 Flash/Mini; reports GSM8K-384 0.848→0.899 and MBPP-384 0.545→0.693 with 1.2x speedup. Directly relevant to sampling/decoding schedule design. arXiv preprint — [NEW] (submission date conflict, see below)
3. 5 | [Exploring More to Solve More: Boosting Diversity in Text Diffusion via Entropy-Based Guidance (SAKE)](https://arxiv.org/abs/2608.00024) — training-free order-2 Rényi/kernel-entropy guidance that dynamically reshapes the sampling distribution for a fidelity/diversity tradeoff; core sampling-schedule contribution. arXiv preprint — [NEW] (submission date conflict, see below)
4. 4 | [REFLEX: Rethinking MoE Inference as Refinement-Aware Compute Allocation in Diffusion LMs](https://arxiv.org/abs/2608.01784) — reframes MoE expert-routing budget around per-token refinement state rather than uniform allocation; efficiency trick specific to DLM inference, submitted to AAAI 2027. arXiv preprint, submitted ~2026-08-03 — [NEW]
5. 4 | [xPress: Parallel Refinement for Diffusion Drafters in Speculative Decoding](https://arxiv.org/abs/2608.02438) — lightweight causal refiner that reconciles a block-diffusion draft (e.g. dFlash) into a jointly-plausible sequence before acceptance, addressing the "marginals not joint distribution" failure mode of block-diffusion drafting. Authors incl. Zheng Wang, Davis Wertheimer, Minjia Zhang. arXiv preprint, submitted ~2026-08-03 — [NEW]

**Couldn't verify:**
- Exact submission date for arXiv 2608.00024 (SAKE) — one retrieved summary said "10 Jul 2026," inconsistent with its 2608 (August) ID prefix; needs a direct arXiv listing-page check next cycle.
- Exact submission date for arXiv 2608.02625 (Speculative Correction) — one retrieved summary said "July 21, 2026," also inconsistent with the ID; content/results are corroborated across multiple hits, the date is not.
- Code/weight release status for all five items above — no GitHub links surfaced for any; tiered as arXiv-preprint-only pending confirmation.

**Unverified claims made by the scout (own inference, not sourced):**
- Framing AURORA-LM as "direct lineage to continuous-latent diffusion LM work" is the scout's own characterization, not a stated claim in the retrieved summaries.
- Framing REFLEX and xPress as tier-4 "plausibly transfer" efficiency tricks is the scout's own relevance judgment, not sourced.
- A search snippet mentioned "Qwen3.8 Max" (Aug 2, 2026) and an "LLM 0.32" tool release (Aug 4, 2026) — excluded as tangential/tooling news, not independently verified beyond a single snippet, and judged non-field-shifting for diffusion-LM research (a judgment call, not a sourced fact).

---

### 2026-08-03 (scan)

Window: 2026-07-30 to 2026-08-03 (since the 2026-07-31 scan). Thin cycle — after
~20 targeted searches across arXiv (cs.CL/cs.LG/cs.AI), Hugging Face Daily
Papers, alphaXiv, and social lead-generators, no diffusion-LM item could be
confirmed with a search-verified submission date strictly inside the window;
most likely search-index lag on very recent arXiv IDs rather than a genuinely
quiet week (this framing is the scout's own inference, not sourced — see
below). 4 items listed, not padded to 8 — per the rubric, a short honest list
beats padding.

1. 5 | [Mean-to-Score Discrete Diffusion: Posterior-Mean Denoisers for Score Entropy](https://arxiv.org/abs/2607.21372) — theoretical unification connecting denoiser/cavity/score parameterizations for discrete diffusion; bears directly on score-entropy-style training objectives (SEDD lineage). arXiv preprint (no code/weights confirmed) — [NEW]
2. 5 | [UNIFUSION: Adapting Autoregressive LMs into Discrete Diffusion under a Unified Reverse-Rate Objective](https://arxiv.org/abs/2607.24507) — expresses SEDD/MDLM/GIDD/M2S/Neural-CTMC losses as one generalized KL objective over reverse rates; continual-pretrains GPT-2 checkpoints into uniform-noise diffusion, reports best-in-class WinoGrande/SIQA/BBH among compared diffusion models. arXiv preprint (no code/weights confirmed) — [NEW]
3. 4 | [Explorative Modeling: Unlocking a Third Pretraining Axis and End-to-End Generation](https://arxiv.org/abs/2607.27372) — Gladstone, Ji, Du (UIUC/Harvard); proposes "exploration" (best-of-K training-time candidate matching) as a scaling axis alongside params/data, claims 4.1x FLOP / 6.2x sample efficiency gains spanning continuous and discrete (language) domains; code released on GitHub. Plausibly transfers to diffusion-LM training. arXiv preprint + code — [NEW]
4. 2 | [COLM 2026 "NonAR-LM" workshop](https://pengzhangzhi.github.io/NonAR-LM/) — dedicated venue for diffusion/flow-matching/any-order generation (Oct 9, 2026, San Francisco); notifications went out July 24; invited talk from Shansan Gong (HKU) on flexible generation order in diffusion LMs. Community/traction signal, not a paper — lab blog / event page — [NEW]

**Couldn't verify:**
- Full abstracts of items #1 and #2 — search surfaced only title/author/reference-context snippets, not primary abstract text.
- Whether #1 or #2 has released code/weights — no GitHub repo surfaced for either; tiered as arXiv-preprint-only, not preprint+code, pending confirmation.
- Whether anything genuinely new was posted to arXiv Aug 1–3 specifically — could not rule out search-index lag; worth a direct `arxiv.org/list/cs.CL/recent` check next cycle instead of relying on search engines alone.

**Unverified claims made by the scout (own inference, not sourced):**
- That items #1 and #2 are companion works from an overlapping author group — inferred from shared names in search snippets, not stated explicitly by either paper.
- That the absence of confirmed 2026-07-30–08-03 items reflects search-index lag rather than a genuinely quiet week — speculation, not sourced.
- That this window's general frontier-LLM releases (DeepSeek-V4-Flash-0731, Claude Opus 5, Gemini 3.6 Flash, GPT-5.6) are non-field-shifting for diffusion-LM research and thus excluded — a judgment call, not a sourced fact (the releases themselves are search-sourced; the exclusion decision is the scout's).

---

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

- **Papers to read:**
  - [Halton Scheduler for Masked Generative Image Transformer](https://arxiv.org/abs/2503.17076) (ICLR 2025) — low-discrepancy, training-free unmasking schedule; test the 1-D text analogue against confidence-based decoding.
  - [Chatterbox-Flash](https://arxiv.org/abs/2605.30748) — marginal-subtracted confidence scoring for parallel unmasking; cheap to try on any dLLM's decoder.
  - [Discrete Neural Flow Samplers](https://arxiv.org/pdf/2505.17741) / [Scalable Discrete Diffusion Samplers](https://arxiv.org/abs/2502.08696) — data-free CTMC samplers from an energy; reframes alignment as sampler design rather than RL-on-samples.
- **People / labs to track (seeded 2026-08-01):**
  - Lindsten group, Linköping University — symmetry-constrained discrete diffusion ([WyckoffDiff](https://proceedings.mlr.press/v267/ekstrom-kelvinius25a.html)); watch for the "design the forward process to match domain corruption" idea generalizing to text.
  - Linderman Lab, Stanford (w/ MSR) — [Informed Correctors / k-Gillespie's](https://arxiv.org/abs/2407.21243), [code](https://github.com/lindermanlab/informed-correctors); model-informed predictor-correctors for low-NFE sampling, directly relevant to dLLM decoding speed.
  - Apple ML Research discrete-sampler line — [Discrete Neural Flow Samplers](https://machinelearning.apple.com/research/discrete-neural-flow); track for reward-tilted sampling as an alternative to GRPO-style dLLM RL.
- **Open questions:**
  - Does a low-discrepancy (Halton-style) unmasking schedule beat confidence-based decoding for text dLLMs? (from finding #2, 2026-08-01 audit)
  - What is the "linguistically natural" corruption process for text diffusion — i.e., is generic uniform masking leaving performance on the table the way it did for ScDiVa (dropout-shaped) and WyckoffDiff (symmetry-shaped)? (from finding #9, 2026-08-01 audit)
- **Predictions (with dates):** _(none yet)_

### Resolved

_(none yet)_

---

## Blind-spot audits (monthly)

<!-- The monthly /diffusion-blindspot run appends a dated section here: adjacent
fields / venues / labs surfaced, citation-expansion clusters, keyword-drift
leads. These become new Watchlist entries. -->

### 2026-08-01 (first blind-spot audit)

Anchor: **MDLM** (current applied non-NLP work forks from it — any BERT-style
domain encoder becomes a generator by reweighting the MLM loss). D3PM pulled
in separately for the materials/symmetry cluster where it's still the cited
root. Full move-by-move detail (citation clusters, keyword-drift search
vocab) lives in the agent transcript; this entry keeps the ranked synthesis.

**Ranked findings (most likely to change how you approach your own work, first):**

1. **Prior-calibrated confidence scoring** (speech TTS) — unmasking confidence is contaminated by token marginals; subtract the block-level marginal before ranking. One-line change, testable tonight on any dLLM. [arXiv 2605.30748](https://arxiv.org/abs/2605.30748) — preprint
2. **Halton / low-discrepancy unmasking schedule** (vision, ICLR'25) — drop confidence-based selection, pick positions via a quasi-random low-discrepancy sequence to decorrelate the parallel batch. Training-free; the 1-D text analogue looks unclaimed. [arXiv 2503.17076](https://arxiv.org/abs/2503.17076) — top-tier
3. **Data-free discrete diffusion samplers from an energy** (ICLR'25 + NeurIPS'25) — reframes dLLM alignment as learning a CTMC rate matrix whose stationary law *is* the reward-tilted distribution, instead of RL on samples. [arXiv 2502.08696](https://arxiv.org/abs/2502.08696), [arXiv 2505.17741](https://arxiv.org/pdf/2505.17741) — top-tier
4. **Edit Flows + CTC-seeded refinement** (NeurIPS'25 / speech) — kills the fixed-canvas/padding assumption via an insert-delete-substitute CTMC; ASR adds "seed with a cheap alignment draft, then refine." [arXiv 2506.09018](https://arxiv.org/abs/2506.09018), [arXiv 2606.28732](https://arxiv.org/abs/2606.28732) — top-tier + preprint
5. **Parallel-in-time Picard sampling** — parallelize over diffusion *steps* rather than tokens; composes with token-parallel decoding, unclaimed in dLLM-land. [arXiv 2607.00773](https://arxiv.org/abs/2607.00773) — preprint
6. **Informed correctors / k-Gillespie's** (NeurIPS'25) — model-informed predictor-corrector; better quality-per-NFE at low step counts. [arXiv 2407.21243](https://arxiv.org/abs/2407.21243), [code](https://github.com/lindermanlab/informed-correctors) — top-tier
7. **Discrete Walk-Jump Sampling** (ICLR'24 Outstanding Paper) — abandon the noise schedule entirely: one noise level, Langevin MCMC in smoothed space, one-step project back. Strongest empirical validation here (wet-lab, 97.5-100% expression success). [arXiv 2306.12360](https://arxiv.org/abs/2306.12360) — top-tier
8. **Amortized twisted SMC (CDM)** — asymptotically exact reward-tilted sampling at <5% overhead; rigorous alternative to GRPO-style dLLM RL. [arXiv 2605.23346](https://arxiv.org/abs/2605.23346) — preprint
9. **Domain-shaped forward processes** (ScDiVa, WyckoffDiff) — design the corruption process to match real data corruption (scRNA dropout) or quotient out invariances (crystal symmetry), instead of generic uniform masking. Open question for text. [arXiv 2602.03477](https://arxiv.org/abs/2602.03477), [arXiv 2502.06485](https://arxiv.org/abs/2502.06485) — top-tier
10. **Gibbs correctors (GADD)** — training-free acceleration for uniform-rate (non-absorbing) models, relevant if revisiting SEDD-style uniform noise for self-correction. [arXiv 2605.27352](https://arxiv.org/abs/2605.27352) — preprint
11. **Fixed-point-iteration one-step distillation** (vision) — a distillation recipe distinct from distribution matching (DiDi-Instruct); vision is ahead of text here. [arXiv 2605.21484](https://arxiv.org/pdf/2605.21484) — preprint
12. **Kinetic-optimal paths / discrete Schrödinger bridges** — principled path design vs. hand-tuned mask schedules; longer-horizon bet. [arXiv 2412.03487](https://arxiv.org/pdf/2412.03487), [arXiv 2509.23348](https://arxiv.org/pdf/2509.23348) — top-tier / preprint
13. **Protein/DNA method-reuse cluster** (MeMDLM, MapDiff, D3-for-DNA) — mostly confirms the MDLM/SEDD toolkit travels; useful as a collaboration surface / wet-lab-grade eval discipline more than a new technique. [MeMDLM](https://openreview.net/forum?id=SeslKuVb6z), [MapDiff](https://www.nature.com/articles/s42256-025-01042-6), [D3](https://www.biorxiv.org/content/10.1101/2024.05.23.595630v3.full) — mixed

**5 unwatched venues/labs/communities (one verified result each):**

- Interspeech/ICASSP + neural-audio-codec community — [ADDSE, Interspeech 2026](https://arxiv.org/abs/2602.22417) (hierarchical RVQ discrete diffusion)
- Lindsten group, Linköping Univ. + ML4Science materials circuit — [WyckoffDiff, ICML 2025](https://proceedings.mlr.press/v267/ekstrom-kelvinius25a.html)
- Neural-sampler / stat-physics community (Imperial + Apple ML Research) — [Discrete Neural Flow Samplers, NeurIPS 2025](https://machinelearning.apple.com/research/discrete-neural-flow)
- Linderman Lab, Stanford + MSR — [Informed Correctors, NeurIPS 2025](https://arxiv.org/abs/2407.21243)
- Virtual-cell/single-cell foundation-model community — [ScDiVa, ICML 2026](https://arxiv.org/abs/2602.03477)
- (bonus) RL/robotics diffusion-policy line — [Awesome-Robotics-Diffusion](https://github.com/showlab/Awesome-Robotics-Diffusion) feed; concrete item [arXiv 2509.22963](https://arxiv.org/abs/2509.22963)

**Couldn't verify / flagged by the scout as its own inference, not sourced:**
- Venue of arXiv 2509.22963 (discrete diffusion RL policies) — OpenReview record exists but acceptance/venue unconfirmed; treat as preprint.
- MapDiff exact publication date conflicting in search snippets (June 2025 vs Feb 2026); journal/DOI solid, date not.
- Chatterbox-Flash (item 1) exact month conflicting (May vs June 2026); arXiv ID implies May.
- ScDiVa's ICML 2026 poster page was search-attested only, not page-confirmed directly.
- "Has not crossed into text diffusion" (Move 2 framing) is the scout's inference from negative search results, not a systematic lit check — highest confidence on Halton scheduling and prior-calibrated confidence being genuinely unclaimed; lowest confidence on variable-length edit modeling, since Edit Flows itself already ran text benchmarks.
- Move 1 cluster sizes are impressionistic (no full citation-graph pull).

---

## Anti-rot rules (enforced by the weekly updater)

1. Every item carries a **date**. No undated entries.
2. The weekly pass must **demote/remove** stale "hot" items — not only add.
   Rot happens when updates only append.
3. Anything not backed by a retrieved source is tagged **`[unconfirmed]`**.
4. "State of play" is **rewritten**, never appended to, and kept ≤10 lines.
5. Resolved watchlist items and cooled threads are moved, not left in place.
