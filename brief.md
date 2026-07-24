# Shared Brief — Diffusion-LM Field Monitoring

*Every agent in this system reads this file first and obeys it. It is the single
source of truth for the relevance rubric, the output contract, and the standing
quality rules. If you change what "matters," change it HERE, not in each agent.*

---

## Mission

Keep a diffusion-language-model researcher current on their field and its
neighbors. The goal is **triage, not coverage** — a handful of items they will
actually read beats a wall of everything. Honesty about what you could NOT
verify is worth more than a longer list.

## Relevance rubric — score every item 1–5 against THIS, then rank

- **5 — core:** discrete / masked / absorbing diffusion for text; any-order or
  non-autoregressive generation; inference-time scaling of diffusion LMs; new
  training objectives (score-entropy-style, D3PM lineage); new sampling /
  remasking schedules; diffusion-LM scaling results vs. autoregressive baselines.
- **3–4 — high:** agent architectures, evals, or decoding / sampling methods
  that plausibly transfer to diffusion LMs; controllable / constrained
  generation; efficiency tricks that could cut sampling steps.
- **1–2 — watch:** general LLM capability / efficiency news, included ONLY if
  clearly field-shifting.

Anchor papers for citation-expansion / adjacency work: **D3PM**, **SEDD**
(score-entropy discrete diffusion), **MDLM** (masked diffusion LM). Adjust in
the prompt if a run needs a different anchor.

## Output contract (keep everything skimmable and diffable)

Default digest line, one per item:

```
score | Title — one line on why it matters to a diffusion-LM researcher — link — [NEW|incremental]
```

- Cap digests at the **top 8–10**. A short honest list beats a padded one.
- "Nothing important this cycle" is a valid, encouraged verdict when true.
- Every dated item carries its source **tier** (see below) so relevance is
  calibratable at a glance.
- End every run with a **"Couldn't verify"** tail: 2–3 things you could not
  confirm and want human eyes on.

## Standing quality rules (non-negotiable)

1. **Recency comes only from web search, never from training memory.** Any
   claim about work dated after 2024 — a model name, a "first/SOTA" claim, a
   benchmark number, a date — must trace to a source retrieved in THIS run, or
   be tagged `[unverified]`. Today's date is provided by the harness; treat
   anything you "remember" as newest as a hypothesis to check, not a fact.
2. **List your own unverified claims.** At the end of every run, enumerate any
   claim you stated that is not backed by a retrieved source. Overconfidence
   shows up as specific-sounding claims with no link — that is the tell.
3. **Traction ≠ attention.** A viral demo with 5k likes and no paper scores
   low; a quiet paper already reproduced twice scores high. Score traction on
   proxies: released code/weights, independent reproductions, follow-up
   adoption, citation/discussion velocity relative to age.
4. **Source tiering** (show the tier next to each claim):
   `peer-reviewed / well-cited` > `arXiv preprint + code` > `arXiv preprint`
   > `lab blog` > `social post`.
5. **Cite every non-obvious claim with a real link** from your results. Never
   invent titles, authors, venues, or URLs. If a detail can't be confirmed, say
   so rather than guess.
6. **Flag disagreements.** Where sources conflict, surface it — that is signal,
   not noise to smooth over.

## Sources (by type, not URL soup)

- **Primary:** arXiv `cs.CL`, `cs.LG`, `cs.AI` new-submission listings and
  targeted search queries; Hugging Face Daily Papers.
- **Aggregators / formal:** alphaXiv, Semantic Scholar, OpenReview, Google
  Scholar.
- **Social / forum (lead generators only, never ground truth):** a named set of
  X accounts, relevant subreddits, Hacker News.

## Files in this system

- `diffusion-llm-tracker.md` — the living doc (state of play, moving-now board,
  changelog, watchlist, blind-spot audits). Fed daily, groomed weekly.
- `brief.md` — this file.
- `README.md` — how the whole system fits together and how to run each piece.
