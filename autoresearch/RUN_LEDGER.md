# AutoResearch Run Ledger

Created: 2026-06-02
Last updated: 2026-09-08
Timezone: America/Phoenix

This ledger indexes AutoResearch runs proposed for canonicalization. A useful output that exists only in chat or another external surface is not considered canonical until explicitly backfilled or committed. Runs on an unmerged review branch remain reviewable/proposed rather than active on `main`.

## Run Index

| Run | Date | Status | Focus | Artifact | Score |
|---|---:|---|---|---|---:|
| 000 | 2026-06-02 | unmaterialized | Bootstrap slot; governance/state created but no run artifact committed | — | — |
| 001 | 2026-06-16 | unmaterialized | Planned integration slot; no canonical run artifact | — | — |
| 002 | 2026-06-30 | unmaterialized | Planned meta-optimization/compaction slot; no canonical run artifact | — | — |
| 003 | 2026-08-11 | completed on review branch | Continuity recovery; harness self-improvement, causal eval, context lifecycle, retrieval sufficiency, Tasks/Ponder update | `runs/2026-08-11_run_003.md` | 28/30 self-score |
| 004 | 2026-08-25 | completed on review branch | Experiment debt; state/supersession memory; harness forgetting; context isolation; interventional diagnosis; ChatGPT/Ponder workspace delta | `runs/2026-08-25_run_004.md` | 25.8/30 self-score |
| 005 | 2026-09-08 | completed on review branch | Evaluation isolation; E004-E006 exposure readiness; event-triggered Tasks; harness tampering/forgetting; context privilege; memory credit assignment | `runs/2026-09-08_run_005.md` | 26.3/30 self-score |

## Continuity Status

Runs 003-005 are recoverable from GitHub on the current draft review branch. PR #1 remains unmerged, so `main` still does not contain these run/state changes.

E003 canonical continuity result as of Run 005: **partial pass**.
- Recoverability: pass.
- GitHub-only previous-state read: pass.
- Activation on canonical branch: pending human decision.

## Ledger Policy

Every run records:
- run id/date/status/focus/artifact;
- score summary;
- doctrine changes;
- experiments evaluated/created;
- next-run queue;
- canonical state/writeback result;
- experiment-debt metrics;
- evaluation-contamination status where held-out data are involved.

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

Capability note:
- `tasks/CHATGPT_TASKS_CAPABILITY_DELTA_2026-08-11.md`

## Run 004 Trial-to-Behavior Conversion

Prior experiment status:
- E003: partial pass.
- E004: ready but unexecuted; historical-retention slice required.
- E005: ready but unexecuted.
- E006: ready but unexecuted.
- E007: reframed to Ponder vs native ChatGPT workspace.
- E008: parked pending experiment-debt reduction.

Key internal finding:
- experiment generation exceeded experiment execution/adjudication.

Proposed doctrine:
- D-AR-016 Experiment Debt Gate
- D-AR-017 Supersession-Aware State
- D-AR-018 Functional Context Isolation
- D-AR-012 amendment candidate: interventional attribution for adaptive trajectories

Reusable policy:
- `policies/STATEFUL_CONTEXT_CONTROL_CONTRACT_V1.md`

Experiment board:
- `experiments/2026-08-25_to_2026-09-08.md`

New experiments:
- E009 State-first memory wrapper
- E010 Functional context isolation

## Run 005 Trial-to-Behavior Conversion

### Internal finding

The frozen E004-E006 evaluation policy requires blind separation between candidate development, held-out execution, and evaluator-only expectations.

The Run 005 governance context necessarily read all three datasets during previous-state inspection, including held-out/evaluator material. Therefore this context cannot validly execute their blind candidate protocol.

The datasets remain intact for future isolated contexts; the current context exposure is not global dataset contamination.

### Prior experiment status after readiness audit

- E003: partial pass.
- E004: **blocked pending isolated evaluator runtime**.
- E005: **blocked pending isolated evaluator runtime**.
- E006: **blocked pending isolated evaluator runtime**; preferred first recovery target.
- E007: reframed; Ponder vs native ChatGPT workspace with typed-action governance measurement.
- E008: parked.
- E009: proposed/unexecuted.
- E010: proposed/unexecuted.

### Proposed doctrine

- D-AR-019 Evaluation Isolation Boundary

Capability amendment candidate:
- D-AR-006 remains "Tasks Are Triggers, Not Canonical State", but trigger taxonomy now includes supported event-triggered Work flows from Gmail, Slack, and GitHub events.

No D-AR-011 through D-AR-018 doctrine was promoted.

### Reusable artifacts

- `policies/EVALUATION_ISOLATION_AND_PROMOTION_CONTRACT_V1.md`
- `evaluations/E004_E006_EXECUTION_READINESS_2026-09-08.md`
- `tasks/CHATGPT_EVENT_TRIGGER_WORKSPACE_DELTA_2026-09-08.md`

### Experiment board

- `experiments/2026-09-08_to_2026-09-22.md`

### New experiment

- E011 Isolated Evaluation Runner

No E012+ was created.

## Experiment Debt — Run 005

```yaml
prior_experiments_e003_e010: 8
partial_results: 1
completed_result_artifacts: 0
blocked_pending_isolated_runtime: 3
reframed: 1
parked: 1
proposed_unexecuted: 2
new_experiments: 1
```

## Current Writeback Result

Run 005 artifacts, proposed state, and this ledger update were written to the existing review branch rather than directly to `main`.

PR #1 remains the human review gate. No doctrine was automatically activated and no merge was performed by Run 005.

## Compaction Milestones

Because Runs 000-002 are unmaterialized, milestone counts use completed recoverable run artifacts beginning with Run 003.

Runs 003-005 now form the first three-run recoverable sequence on the review branch, so this `STATE.md` update serves as the **first review-branch compaction**.

It remains proposed until the review history is accepted. If PR #1 is rejected/superseded, recalculate milestones from the accepted canonical sequence.

If Runs 003-005 become accepted canonical history:
- next full governance audit after Run 008 (six accepted runs beginning at Run 003).

## Next Run Acceptance Gate

Run 006 should prioritize:
1. human continuity closure;
2. E011 isolated evaluator runtime;
3. at least two valid result artifacts among E004/E005/E006;
4. E009 when evaluation infrastructure is usable;
5. experiment-debt metrics;
6. only then another full frontier expansion.

## Status Values

- planned
- running
- completed
- compacted
- failed
- archived
- unmaterialized
- blocked

`completed on review branch` is descriptive in the table; active canonical status still depends on the review decision.
