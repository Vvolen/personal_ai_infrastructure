# State Reconciliation and Verifiable Evaluation Contract v1

Created: 2026-09-22  
Status: proposed  
Linked run: `autoresearch/runs/2026-09-22_run_006.md`
Review correction: 2026-10-07, E011-B precommitment timing; status remains proposed.

## Purpose

Prevent two distinct governance failures:

1. a canonical state snapshot becoming semantically stale after authoritative external events;
2. an isolated evaluator confidently measuring the wrong construct.

## Part A — State Reconciliation

### Authority order

For claims about repository state:

1. immutable/event-native repository facts: merge status, commit ancestry, current refs;
2. versioned policy and run artifacts;
3. compacted state snapshots such as `STATE.md`;
4. derived dashboards/cockpits;
5. ambient chat memory.

A lower layer may summarize a higher layer. It may not override a fresher contradictory higher-layer fact.

### Preflight reconciliation

Before frontier research:

```yaml
state_reconciliation:
  run_id:
  checked_at:
  canonical_repo:
  snapshot_commit:
  latest_main_commit:
  latest_run_artifact:
  open_review_items: []
  event_assertions: []
  snapshot_assertions: []
  conflicts: []
  resolution_actions: []
  reconciliation_status: clean | repaired | blocked
```

Mandatory checks:
- latest `main` commit;
- current PR status for any review gate referenced in state;
- existence of the latest run artifact;
- status of P0 experiments;
- whether `STATE.md` asserts an event that has since changed.

### Conflict rule

If a snapshot says `PR #1 = unmerged` and GitHub says `merged=true`, GitHub event state wins immediately.

The stale snapshot is then:
- marked stale;
- corrected in the next reviewable writeback;
- preserved in history rather than silently erased.

## Part B — Verifiable Evaluation

### Outcome hierarchy

Prefer, in order:

1. machine-verifiable invariant or task completion;
2. external environment receipt/state;
3. deterministic artifact validator;
4. calibrated behavioral rubric;
5. calibrated LLM judge;
6. subjective satisfaction.

This is not a claim that lower levels are useless. It is a rule that a lower-level proxy cannot overrule contradictory higher-level evidence without an explicit exception.

### Judge calibration record

```yaml
judge_calibration:
  task_family:
  grounded_signal:
  judge_version:
  sample_size:
  ranking_agreement:
  construct_agreement:
  false_positive_rate:
  close_pair_disagreement:
  valid_range:
  abstain_when:
  precommitment_ref:
  precommitment_commit:
  precommitment_sha256:
  calibration_manifest_sha256:
  evaluation_manifest_sha256:
  thresholds_and_scoring_version:
  frozen_before_any_outputs: true | false
  last_calibrated_at:
```

### Promotion rule

A candidate cannot be promoted solely by an LLM-judge score when:
- a grounded success signal exists and the candidate fails it;
- the judge is uncalibrated for the task family;
- close-pair disagreement exceeds the precommitted threshold;
- the evaluator construct differs from the real objective.

## Part C — E011 Runtime Gate

Before E004–E006 are released:

### E011-A
Run a synthetic isolation fixture and prove:
- R1 cannot read held-out/evaluator assets;
- R2 cannot read evaluator keys;
- R3 receives outputs only after freeze;
- a seeded policy violation is detected;
- all exposure receipts are complete.

### E011-B
Use `autoresearch/evaluations/E011_B_PRECOMMITMENT_V1.md`. Before generating or inspecting any calibration or evaluation outputs, record an immutable attempt-specific precommitment fixing task/group split, numeric abstention thresholds, all evaluator versions, and the pass/fail calculation. Calibration cannot tune these choices within the same attempt. Measure release eligibility on the untouched evaluation split only; preserve separate calibration diagnostics.

Missing or late precommitment, unknown exposure, changed parameters, or undefined denominators cannot pass. Failed grounded completion cannot be overridden by judge score alone. A1's policy-only result is insufficient: B remains blocked until A2 demonstrates real isolation. Reviewed A2/B passes permit E004–E006 recovery attempts; full E011 completion still requires its original two-result and overhead/receipt gates.

## Result Receipt Additions

```yaml
result_receipt:
  state_reconciliation_receipt:
  grounded_outcome:
    signal_type:
    value:
    verifier:
    verifier_version:
  judge_outcome:
    score:
    calibrated: true | false
    calibration_ref:
  disagreement:
    exists:
    resolution_rule:
  promotion_eligible:
```

## Relationship to Existing Doctrine

Proposed amendment to D-AR-004:
- snapshots are reconciled projections of the governance control plane, not superior to fresher event-native facts.

Proposed amendment to D-AR-010:
- grounded/verifiable task completion is primary when available; trace/artifact/judge evaluation remains necessary for dimensions the grounded signal cannot express.

This contract does not promote either amendment automatically.
