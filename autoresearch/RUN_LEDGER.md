# AutoResearch Run Ledger

Created: 2026-06-02
Timezone: America/Phoenix

This ledger indexes every biweekly AutoResearch run.

## Run Index

| Run | Date | Status | Focus | Artifact |
|---|---:|---|---|---|
| 000 | 2026-06-02 | planned | Bootstrap AutoResearch governance loop | `runs/2026-06-02_run_000_bootstrap.md` |
| 001 | 2026-06-16 | planned | Test first experiments and integrate findings | `runs/2026-06-16_run_001.md` |
| 002 | 2026-06-30 | planned | Meta-optimize loop and compact first three runs | `runs/2026-06-30_run_002.md` |

## Ledger Policy

Every run must add a new row with:

- run id
- date
- status
- focus
- artifact path
- score summary
- doctrine changes
- next-run queue

## Compaction Milestones

- After Run 002: update `STATE.md` with first compaction.
- After Run 005: governance audit.
- After Run 008: second compaction and task redesign.

## Status Values

- planned
- running
- completed
- compacted
- failed
- archived
