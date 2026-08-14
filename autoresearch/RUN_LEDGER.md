# AutoResearch Run Ledger

Created: 2026-06-02
Last updated: 2026-08-11
Timezone: America/Phoenix

This ledger indexes canonical AutoResearch runs. A useful output that exists only in chat or another external surface is not considered a canonical run artifact until it is explicitly backfilled or committed.

## Run Index

| Run | Date | Status | Focus | Artifact | Score |
|---|---:|---|---|---|---:|
| 000 | 2026-06-02 | unmaterialized | Bootstrap slot; governance/state were created but no run artifact was committed | — | — |
| 001 | 2026-06-16 | unmaterialized | Planned integration slot; no canonical run artifact | — | — |
| 002 | 2026-06-30 | unmaterialized | Planned meta-optimization/compaction slot; no canonical run artifact | — | — |
| 003 | 2026-08-11 | completed | Continuity recovery; harness self-improvement, causal eval, context lifecycle, retrieval sufficiency, Tasks/Ponder update | `runs/2026-08-11_run_003.md` | 28/30 self-score |

## Continuity Recovery Note

The June bootstrap defined a 14-day cadence and planned Run 000-002, but no `autoresearch/runs/` directory existed on `main` as of 2026-08-11. The first three slots are therefore marked `unmaterialized` rather than `failed`: the repository cannot prove whether research occurred elsewhere, only that no canonical artifacts or evaluations were written back.

Run 003 is intentionally written through a reviewable branch/PR together with the state compaction and ledger repair. Future scheduled runs should treat successful writeback as part of run acceptance.

## Ledger Policy

Every run must record:

- run id
- date
- status
- focus
- artifact path
- score summary
- doctrine changes
- experiments evaluated/created
- next-run queue
- canonical state/writeback result

## Run 003 Doctrine Changes

Proposed additions/modifications:

- D-AR-011 Frozen Outer Anchor
- D-AR-012 Attribution Before Promotion
- D-AR-013 Interface-State Separation
- D-AR-014 Harness Exposure Policy
- D-AR-015 Evidence-Sufficiency Retrieval

Reusable policy: `policies/HARNESS_EVOLUTION_CONTRACT_V1.md`

Experiment board: `experiments/2026-08-11_to_2026-08-25.md`

Tasks delta: `tasks/CHATGPT_TASKS_CAPABILITY_DELTA_2026-08-11.md`

## Compaction Milestones

The planned compaction after Run 002 did not occur because Runs 000-002 were not materialized. Run 003 therefore performs a continuity-recovery compaction in `STATE.md` while explicitly preserving the gap.

Future milestones should be counted from canonical completed runs:

- After Run 005: next three-run doctrine compaction (Runs 003-005 are the first three canonical completed runs).
- After Run 008: six-run governance audit (Runs 003-008) and task redesign if warranted.

## Status Values

- planned
- running
- completed
- compacted
- failed
- archived
- unmaterialized — scheduled/planned slot with no canonical run artifact; does not imply the research was or was not attempted elsewhere
