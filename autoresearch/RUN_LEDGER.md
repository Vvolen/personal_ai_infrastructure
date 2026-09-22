# AutoResearch Run Ledger

Created: 2026-06-02
Last updated: 2026-09-22
Timezone: America/Phoenix

This ledger indexes AutoResearch runs proposed for or accepted into canonical history. Useful output that exists only in chat or another external surface is not canonical until committed. Review branches remain proposed until merged or otherwise explicitly accepted.

## Run Index

| Run | Date | Status | Focus | Artifact | Score |
|---|---:|---|---|---|---:|
| 000 | 2026-06-02 | unmaterialized | Bootstrap slot; governance/state created but no run artifact committed | — | — |
| 001 | 2026-06-16 | unmaterialized | Planned integration slot; no canonical run artifact | — | — |
| 002 | 2026-06-30 | unmaterialized | Planned meta-optimization/compaction slot; no canonical run artifact | — | — |
| 003 | 2026-08-11 | canonical | Continuity recovery; harness self-improvement, causal eval, context lifecycle, retrieval sufficiency, Tasks/Ponder update | `runs/2026-08-11_run_003.md` | 28/30 self-score |
| 004 | 2026-08-25 | canonical | Experiment debt; state/supersession memory; harness forgetting; context isolation; interventional diagnosis; ChatGPT/Ponder workspace delta | `runs/2026-08-25_run_004.md` | 25.8/30 self-score |
| 005 | 2026-09-08 | canonical | Evaluation isolation; E004-E006 readiness; event-triggered Tasks; harness tampering; context privilege; memory credit assignment | `runs/2026-09-08_run_005.md` | 26.3/30 self-score |
| 006 | 2026-09-22 | completed on review branch | State/event reconciliation; grounded evaluation; replay-world AutoResearch; kernel memory; procedural memory; retrieval index evolution | `runs/2026-09-22_run_006.md` | 27.5/30 self-score |

## Continuity Status

PR #1 was merged on 2026-09-09. Merge commit: `f71c5b501df32c4655e5d96f9a2cb0f454b2e295`.

Runs 003–005 are therefore canonical on `main`.

E003 — Canonical Continuity Writeback: **PASS**.
- Recoverability: pass.
- GitHub-only previous-state read: pass.
- Activation on canonical branch: pass.

Run 006 discovered that the 2026-09-08 state/ledger snapshots were not reconciled after the merge and still described PR #1 as unmerged. This is recorded as a state-reconciliation failure mode, not an E003 continuity failure.

## Ledger Policy

Every run records:
- run id/date/status/focus/artifact;
- score summary;
- doctrine changes/amendments;
- experiments evaluated/created/advanced;
- next-run queue;
- canonical state/writeback result;
- experiment-debt metrics;
- evaluation-contamination status where held-out data are involved;
- state-reconciliation conflicts when snapshot assertions disagree with fresher authoritative events.

## Run 003 Changes

Proposed doctrine:
- D-AR-011 Frozen Outer Anchor
- D-AR-012 Attribution Before Promotion
- D-AR-013 Interface-State Separation
- D-AR-014 Harness Exposure Policy
- D-AR-015 Evidence-Sufficiency Retrieval

Reusable policy:
- `policies/HARNESS_EVOLUTION_CONTRACT_V1.md`

Experiment board:
- `experiments/2026-08-11_to_2026-08-25.md`

## Run 004 Trial-to-Behavior Conversion

Key internal finding:
- experiment generation exceeded experiment execution/adjudication.

Proposed doctrine:
- D-AR-016 Experiment Debt Gate
- D-AR-017 Supersession-Aware State
- D-AR-018 Functional Context Isolation
- D-AR-012 amendment candidate: interventional attribution for adaptive trajectories

Reusable policy:
- `policies/STATEFUL_CONTEXT_CONTROL_CONTRACT_V1.md`

New experiments:
- E009 State-first memory wrapper
- E010 Functional context isolation

## Run 005 Trial-to-Behavior Conversion

Key internal finding:
- candidate development, held-out execution, evaluator-only expectations, and promotion authority require real context/tool isolation.

Prior experiment status after readiness audit:
- E003: partial pass at the time of Run 005; later closed by PR #1 merge.
- E004: blocked pending isolated evaluator runtime.
- E005: blocked pending isolated evaluator runtime.
- E006: blocked pending isolated evaluator runtime; preferred first recovery target.
- E007: reframed Ponder vs native ChatGPT workspace.
- E008: parked.
- E009: proposed/unexecuted.
- E010: proposed/unexecuted.

Proposed doctrine:
- D-AR-019 Evaluation Isolation Boundary

Reusable artifacts:
- `policies/EVALUATION_ISOLATION_AND_PROMOTION_CONTRACT_V1.md`
- `evaluations/E004_E006_EXECUTION_READINESS_2026-09-08.md`
- `tasks/CHATGPT_EVENT_TRIGGER_WORKSPACE_DELTA_2026-09-08.md`

New experiment:
- E011 Isolated Evaluation Runner

No E012+ created.

## Run 006 Trial-to-Behavior Conversion

### Internal finding

PR #1 was merged after the prior snapshot was written, but `STATE.md` and this ledger still asserted the pre-merge condition. A state file can be canonical and still be stale about events it summarizes.

### Experiment result

- E003: **PASS** after event reconciliation.

### Prior experiment status

- E004: blocked pending E011.
- E005: blocked pending E011.
- E006: blocked pending E011; first recovered real experiment.
- E007: reframed; contingent on Ponder access.
- E008: parked.
- E009: proposed/unexecuted.
- E010: proposed/unexecuted.
- E011: P0; advanced into E011-A isolation dry run and E011-B grounded-eval calibration.

### Doctrine amendments proposed

No new D-AR identifier was created.

- D-AR-004 amendment candidate: reconcile state snapshots against fresher authoritative repository events before use.
- D-AR-010 amendment candidate: grounded/machine-verifiable completion is primary when available; LLM-judge scores are auxiliary and calibrated.

### Reusable artifacts

- `policies/STATE_RECONCILIATION_AND_VERIFIABLE_EVAL_CONTRACT_V1.md`
- `evaluations/STATE_RECONCILIATION_RECEIPT_2026-09-22.md`
- `experiments/2026-09-22_to_2026-10-06.md`

### Frontier mechanisms queued, not promoted

- Dream-RSI-style discovery-history replay;
- kernel-managed shared memory;
- self-evolving search indices;
- procedural graphs / functional memory units;
- matched-replay procedural skill evolution;
- grounded verification hierarchy.

### Experiment debt after Run 006

```yaml
closed_results:
  E003: pass
completed_substantive_result_artifacts_e004_e010: 0
blocked_pending_isolated_runtime:
  - E004
  - E005
  - E006
reframed:
  - E007
parked:
  - E008
proposed_unexecuted:
  - E009
  - E010
p0_runtime:
  - E011
new_experiment_ids: 0
```

## Current Writeback Result

Run 006 artifacts and reconciled state/ledger are on branch `autoresearch/run-006-2026-09-22` pending human review. No doctrine amendment is automatically active merely because it appears in this branch.

## Compaction Milestones

Runs 003–005 form the first three-run accepted sequence and the first canonical compaction.

Next full governance audit: after Run 008, assuming Runs 006–008 are accepted.

## Next Run Acceptance Gate

Run 007 should prioritize:
1. decision on Run 006 reconciliation changes;
2. E011-A isolated evaluator dry run;
3. E011-B grounded evaluation calibration;
4. valid E006 result artifact;
5. E005 then E004;
6. E009 after evaluator infrastructure works;
7. bounded frontier freshness only after the above.

## Status Values

- planned
- running
- completed
- canonical
- completed on review branch
- compacted
- failed
- archived
- unmaterialized
- blocked
