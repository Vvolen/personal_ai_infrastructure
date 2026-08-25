# AutoResearch Run Ledger

Created: 2026-06-02
Last updated: 2026-08-25
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

## Continuity Status

Runs 003 and 004 are both recoverable from GitHub on the current draft review branch. The PR remains unmerged, so `main` still does not contain these run/state changes.

E003 canonical continuity result as of Run 004: **partial pass**.
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
- experiment-debt metrics.

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
- E007: reframed to Ponder vs ChatGPT Project + Site + Computer History.
- E008: parked pending experiment-debt reduction.

Key internal finding:
- experiment generation currently exceeds experiment execution/adjudication.

Proposed doctrine:
- D-AR-016 Experiment Debt Gate
- D-AR-017 Supersession-Aware State
- D-AR-018 Functional Context Isolation
- D-AR-012 amendment candidate: interventional attribution for adaptive trajectories

No prior proposed doctrine was promoted in Run 004 because the linked local experiments remain unexecuted.

Reusable policy:
- `policies/STATEFUL_CONTEXT_CONTROL_CONTRACT_V1.md`

Experiment board:
- `experiments/2026-08-25_to_2026-09-08.md`

Capability note:
- `tasks/CHATGPT_CONTEXT_WORKSPACE_DELTA_2026-08-25.md`

New experiments:
- E009 State-first memory wrapper
- E010 Functional context isolation

## Experiment Debt — Run 004

```yaml
prior_experiments_e003_e008: 6
partial_results: 1
completed_result_artifacts: 0
ready_unexecuted: 3
reframed: 1
parked: 1
new_experiments: 2
```

## Compaction Milestones

Because Runs 000-002 are unmaterialized, milestone counts use completed recoverable run artifacts beginning with Run 003.

If the current review PR is merged or otherwise accepted as canonical history:
- after Run 005: first three-run doctrine compaction for Runs 003-005;
- after Run 008: six-run governance audit for Runs 003-008.

If the PR is rejected/superseded, recalculate milestones from the accepted canonical sequence rather than silently counting rejected runs.

## Next Run Acceptance Gate

Run 005 should prioritize:
1. human continuity closure;
2. at least two result artifacts among E004/E005/E006;
3. E009 precommit/execution;
4. experiment-debt metrics;
5. only then a full frontier expansion.

## Status Values

- planned
- running
- completed
- compacted
- failed
- archived
- unmaterialized

`completed on review branch` is descriptive in the table; active canonical status still depends on the review decision.
