# Evaluation Isolation and Promotion Contract v1

Created: 2026-09-08
Status: proposed
Owner: AutoResearch governance loop
Linked run: `autoresearch/runs/2026-09-08_run_005.md`

## Purpose

Make held-out evaluation a real runtime boundary rather than an instruction that a long-lived agent is expected to remember not to violate.

This contract exists because the frozen E004-E006 datasets are valid historical evaluation assets, but a context that has already read held-out prompts or evaluator-only expectations cannot later serve as a blind candidate developer or evaluator for those same cases.

## Core rule

> Candidate development, held-out execution, evaluator-only expectations, and promotion authority must be separated by enforceable context and tool boundaries.

"Do not look at the held-out set" is not an evaluation boundary.

## Roles

### R0 — Dataset steward

Responsibilities:
- owns the immutable precommit manifest;
- verifies hashes and exposure logs;
- versions contaminated or corrected datasets;
- does not develop candidate harness changes from held-out contents.

Allowed reads:
- development prompts;
- held-out prompts;
- evaluator keys;
- manifests and hashes.

Allowed writes:
- new dataset versions and contamination records only.

### R1 — Evolver / candidate developer

Responsibilities:
- diagnoses development failures;
- proposes minimal harness changes;
- freezes the candidate version and expected causal mechanism before held-out execution.

Allowed reads:
- governance contract;
- development split;
- baseline development results;
- development evaluator feedback;
- permitted source material.

Forbidden reads:
- held-out prompts before candidate freeze;
- held-out evaluator expectations;
- hidden promotion keys.

Forbidden writes:
- evaluation datasets;
- evaluator rules;
- promotion receipts.

### R2 — Held-out runner

Responsibilities:
- executes frozen baseline and candidate against held-out tasks;
- records complete traces, tool manifests, model snapshot, environment, timestamps, and outputs.

Allowed reads:
- frozen candidate profile/version;
- held-out task stimuli;
- execution contract;
- permitted tools/sources.

Forbidden reads:
- evaluator-only expectations;
- candidate-development notes that reveal test-specific fixes;
- promotion decision criteria beyond public protected metrics.

Forbidden writes:
- candidate harness;
- held-out dataset;
- evaluator key.

### R3 — Evaluator

Responsibilities:
- receives frozen outputs and traces after execution;
- applies the evaluator-only expectations and scoring rubric;
- emits a signed result record;
- reports uncertainty and causal limits.

Allowed reads:
- outputs and traces;
- evaluator-only expectations;
- evaluation tuple;
- protected metrics.

Forbidden writes:
- candidate harness;
- dataset;
- raw execution history.

### R4 — Promoter / human review gate

Responsibilities:
- compares evidence against doctrine promotion requirements;
- verifies contamination status, rollback pointer, and protected regressions;
- records promote / reject / retest / rollback.

The promoter may not treat evaluator score alone as authorization to change L0 governance.

## Exposure receipt

Every role invocation records:

```yaml
exposure_receipt:
  run_id:
  experiment_id:
  actor_or_context_id:
  role: R0 | R1 | R2 | R3 | R4
  started_at:
  ended_at:
  readable_paths: []
  readable_secret_or_hidden_keys: []
  writable_paths: []
  dataset_version:
  candidate_version:
  model_snapshot:
  tool_manifest_hash:
  environment_manifest_hash:
  contamination_detected: false
  contamination_reason:
```

## Candidate freeze receipt

Before held-out release:

```yaml
candidate_freeze:
  experiment_id:
  baseline_profile_version:
  candidate_profile_version:
  candidate_commit_sha:
  target_component:
  minimal_diff:
  causal_hypothesis:
  development_metrics: {}
  frozen_at:
  held_out_unseen_by_evolver: true
```

If `held_out_unseen_by_evolver` cannot be established, the run may still be useful diagnostically but cannot claim blind held-out evidence.

## Result receipt

```yaml
result_receipt:
  experiment_id:
  dataset_version:
  baseline_version:
  candidate_version:
  evaluation_tuple:
    model_snapshot:
    tool_manifest_hash:
    environment_manifest_hash:
    evaluator_version:
    dataset_split:
  metrics_baseline: {}
  metrics_candidate: {}
  protected_regressions: {}
  contamination_status: clean | contaminated | unknown
  causal_confidence:
  negative_results_preserved: true
  decision_recommendation: promote | reject | retest | rollback
  evaluator_actor_id:
  recorded_at:
```

## Contamination policy

A held-out claim is invalid if any of the following occurs before candidate freeze:
- the evolver sees held-out prompts;
- evaluator-only expectations enter the evolver context;
- the candidate is tuned after held-out behavior is observed;
- the evaluator or runner mutates the candidate during execution;
- a dataset file changes without a new version/hash receipt.

Contamination does **not** require deleting the data. Preserve the run as diagnostic evidence, mark it contaminated, and create a new held-out version before making a generalization claim.

## Promotion policy

A change may be promoted only if:
1. development and held-out roles were isolated;
2. candidate version was frozen before held-out release;
3. evaluator-only expectations were withheld from runner/evolver;
4. all evaluation tuple fields are recorded;
5. protected regressions remain inside tolerance;
6. negative/null results are retained;
7. causal confidence is sufficient for the impact class;
8. rollback is available;
9. human review authorizes the promotion when required by L0.

## E004-E006 recovery plan

The current E004-E006 v1 datasets remain useful **only for a future isolated execution context that has not received the held-out prompts/evaluator-only expectations during candidate development**.

Recommended order:

1. Start with E006 because its candidate surface is narrow: evidence-sufficiency stopping.
2. Instantiate an R1 evolver with the development split only.
3. Freeze the stop-policy candidate and causal hypothesis.
4. Instantiate a separate R2 runner for held-out cases.
5. Instantiate R3 only after outputs/traces are frozen.
6. Store result receipt and contamination receipt.
7. Repeat for E005 and E004.

The 2026-09-08 AutoResearch context itself is **exposed** to all E004-E006 held-out/evaluator materials and therefore may not serve as their blind R1/R2 context.

## Relationship to existing doctrine

This contract operationalizes:
- D-AR-010 Trace + Artifact Evaluation;
- proposed D-AR-012 Attribution Before Promotion;
- proposed D-AR-016 Experiment Debt Gate.

It proposes:
- D-AR-019 Evaluation Isolation Boundary.

## References

- `autoresearch/evaluations/E004_E006_PRECOMMIT_MANIFEST_V1.md`
- `autoresearch/policies/HARNESS_EVOLUTION_CONTRACT_V1.md`
- `autoresearch/policies/STATEFUL_CONTEXT_CONTROL_CONTRACT_V1.md`
