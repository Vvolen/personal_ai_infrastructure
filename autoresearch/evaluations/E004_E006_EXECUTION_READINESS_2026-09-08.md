# E004-E006 Execution Readiness — 2026-09-08

Status: governance readiness record
Linked run: `autoresearch/runs/2026-09-08_run_005.md`

## Summary

The v1 precommit artifacts remain intact and useful, but the current AutoResearch execution context cannot validly run the blind candidate-development/held-out protocol because it has already read:

- all E004 held-out prompts;
- all E005 held-out fixtures and evaluator-only expectations;
- all E006 held-out questions/evidence targets.

This is a **runtime isolation problem**, not a dataset-definition failure.

## Current classification

| Experiment | Dataset | Data integrity | Current-context blindness | Status |
|---|---|---|---|---|
| E004 | v1 frozen | intact | failed | blocked pending isolated runner |
| E005 | v1 frozen | intact | failed | blocked pending isolated runner |
| E006 | v1 frozen | intact | failed | blocked pending isolated runner |

## Important distinction

The datasets are **not globally contaminated** merely because this governance context has read them.

They remain valid for a future R1 candidate-development context that receives only the development split, followed by separate R2/R3 held-out execution/evaluation contexts.

Any candidate tuned using this current context would contaminate the held-out claim for that candidate.

## Required runtime properties

Before E004-E006 resume:

1. R1 cannot read held-out prompts or evaluator-only expectations.
2. Candidate version and causal hypothesis freeze before held-out release.
3. R2 cannot read evaluator-only expectations.
4. R3 cannot mutate candidate, dataset, or execution trace.
5. Every role has an exposure receipt.
6. Dataset hash/version is verified before the run.
7. Any accidental exposure marks that result contaminated rather than being hidden.

## Preferred recovery sequence

Start with E006:
- narrow candidate surface;
- clean fixed-budget baseline;
- evidence-sufficiency candidate;
- straightforward query/source/stop trace.

Then E005:
- evaluate whether trajectory access improves defect localization and prevents false promotion.

Then E004:
- broader harness-evolution test after the isolation runtime has proven reliable.

## Governing consequence

Run 005 introduces E011 — Isolated Evaluation Runner — as the P0 experiment needed to convert E004-E006 from "ready but unexecuted" into valid experiments.
