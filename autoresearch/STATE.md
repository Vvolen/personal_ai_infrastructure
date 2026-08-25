# AutoResearch State

Last updated: 2026-08-25
Timezone: America/Phoenix
Status: active — continuity recovery + experiment-debt reduction
Canonical repository: `Vvolen/personal_ai_infrastructure`
Latest proposed run: `autoresearch/runs/2026-08-25_run_004.md`
Review branch: `autoresearch/run-003-2026-08-11`

## Continuity Note

Runs 000-002 remain unmaterialized. Run 003 and Run 004 are recoverable from GitHub on the review branch/PR, but the PR remains unmerged, so these proposed state changes are not yet active on `main`.

Run 004 successfully recovered prior state from GitHub without chat reconstruction. E003 therefore partially passes on recoverability, but activation remains pending human merge/reject/supersede decision.

## Doctrine Status Boundary

- **Active doctrine** is approved canonical operating policy.
- **Proposed doctrine** may shape linked experiments but cannot govern its own promotion.
- Promotion requires linked validation evidence, a recorded decision, and human review.

## Active Doctrine

### D-AR-001 — Prior State First
Every run reads canonical prior state before frontier research.

### D-AR-002 — Epistemic Separation
Load-bearing claims are distinguished as Fact, Inference, Speculation, or Recommendation.

### D-AR-003 — Behavior Change, Not Notes
A run is incomplete unless it produces a reusable artifact, evaluated change, or falsifiable experiment capable of changing future behavior.

### D-AR-004 — GitHub as Governance Control Plane
GitHub or an explicitly superseding ledger is authoritative for doctrine, policies, run history, and versioned decisions. Ambient/chat memory is supporting recall.

### D-AR-005 — Context Is a System
Prompts are one layer of a broader context system: canonical state, evidence, tools, permissions, working context, skills, memory, and compaction.

### D-AR-006 — Tasks Are Triggers, Not Canonical State
Scheduled Tasks are for cadence, monitoring, reminders, and delivery. Every governed run re-reads external canonical state.

### D-AR-007 — Broad Recall, Narrow Commitment
Retrieval may be exploratory. Durable memory writes must be typed, source-grounded, scoped, reversible, and governed by promotion.

### D-AR-008 — Memory / Context Is a Lifecycle
Design memory around architecting, ingesting, scoping, anticipating, retrieving, compacting/consolidating, and forgetting while preserving provenance.

### D-AR-009 — Task-Specific Harnesses
Prefer versioned harness profiles for materially different task families rather than one monolithic global prompt. Change the narrowest relevant layer first.

### D-AR-010 — Trace + Artifact Evaluation
Evaluate both final artifacts and execution trajectories. A correct answer reached through an invalid process can still be a system failure.

## Proposed Doctrine — Run 003

### D-AR-011 — Frozen Outer Anchor
Status: proposed; validate through E004/E005 + human review.

Ordinary runs may evolve task harnesses and bounded evolver policies but may not automatically rewrite governance/evidence/safety anchors.

### D-AR-012 — Attribution Before Promotion
Status: proposed; validate through E005 + human review.

High-impact harness changes require evidence that the changed component plausibly caused the gain.

Run 004 amendment candidate: for adaptive trajectories, post-hoc trace inspection is not sufficient alone; use replay, controlled interventions, ablations, leave-one-out, or counterfactual probes where feasible.

### D-AR-013 — Interface-State Separation
Status: proposed; validate through E007 + human review.

Ponder, ChatGPT Sites/Projects, dashboards, and similar workspaces are human-facing projections over canonical state, not authority for that state.

### D-AR-014 — Harness Exposure Policy
Status: proposed; validate through security/exposure measurements + human review.

Treat valuable harness logic, evolution policy, and evaluator design as scoped security/IP surfaces.

### D-AR-015 — Evidence-Sufficiency Retrieval
Status: proposed; validate through E006 + human review.

Use fixed retrieval budgets as hard safety caps, not mandatory quotas. Escalate only when expected evidence gain justifies cost.

## Proposed Doctrine — Run 004

### D-AR-016 — Experiment Debt Gate
Status: proposed; validate through Run 004/005 operating behavior + human review.

Before creating new doctrine candidates or more than two new experiments, each run must resolve, execute, explicitly park, or fail prior P0 experiments and record experiment-debt metrics.

### D-AR-017 — Supersession-Aware State
Status: proposed; validate through E009 + human review.

Durable state for mutable facts, constraints, decisions, plans, and preferences must represent revision semantics and resolve current state before historical recall influences action.

Minimum fields: `valid_from`, `valid_to`, `supersedes`, `superseded_by`, `depends_on`, `status`, `source_refs`.

### D-AR-018 — Functional Context Isolation
Status: proposed; validate through E010 + human review.

Long-horizon agents should separate governance/identity, objective/plan state, execution scratch, evidence/provenance, and ambient/history cues. Subtask traces do not automatically enter persistent plan state.

## Current Reusable Policies

- `autoresearch/policies/HARNESS_EVOLUTION_CONTRACT_V1.md` — proposed; awaits E004/E005.
- `autoresearch/policies/STATEFUL_CONTEXT_CONTROL_CONTRACT_V1.md` — proposed; awaits E009/E010.

## Active Hypotheses

### H001 — AutoResearch can upgrade personal AI use
Confidence: medium-high. Longitudinal local evidence remains insufficient.

### H002 — Doctrine + experiments are the compounding mechanism
Confidence: high. Current weakness is low experiment execution conversion.

### H003 — GitHub should be control plane; Ponder/Sites/Projects should be interfaces
Confidence: high. Reframed E007 compares Ponder with ChatGPT Project + Site + Computer History over identical GitHub state.

### H004 — Bounded task-specific harness evolution beats monolithic self-editing
Confidence: medium-high. Needs E004.

### H005 — Causal/interventional attribution improves harness promotion decisions
Confidence: medium. Needs E005.

### H006 — Evidence-sufficiency stopping can reduce retrieval cost without quality loss
Confidence: medium-high. Needs E006.

### H007 — Supersession resolution materially improves mutable-state memory
Confidence: medium-high from external evidence; local validation E009 required.

### H008 — Functional context isolation reduces drift/context cost
Confidence: medium-high from external evidence; local validation E010 required.

## Active Experiments

### E003 — Canonical continuity writeback
Status: partial pass.
Recoverability succeeded; activation awaits human PR decision.

### E004 — Bounded task-specific harness evolution
Status: ready but unexecuted.
Add historical-retention slice before execution.

### E005 — Attribution before promotion
Status: ready but unexecuted.
Use frozen precommitted dataset.

### E006 — Evidence-sufficiency retrieval
Status: ready but unexecuted.
Use frozen precommitted dataset and hard caps.

### E007 — Cognitive cockpit
Status: reframed; contingent on Ponder access.
Compare Ponder with ChatGPT Project + Site + Computer History; GitHub remains shared canonical state.

### E008 — Voice-to-project intake
Status: parked until at least two of E004-E006 have result artifacts, unless it becomes an immediate bottleneck.

### E009 — State-first memory wrapper
Status: proposed.
Compare retrieval-only memory with the same backend plus explicit supersession resolver.

### E010 — Functional context isolation
Status: proposed.
Compare flat accumulated context with isolated plan / execution / evidence planes.

Full current board: `autoresearch/experiments/2026-08-25_to_2026-09-08.md`.

## Experiment Debt

```yaml
prior_experiments_e003_e008: 6
partial_results: 1
completed_result_artifacts: 0
ready_unexecuted: 3
reframed: 1
parked: 1
new_experiments_run004: 2
```

## Open Questions

1. Will the current review PR be merged, rejected, or superseded?
2. Does `HARNESS_EVOLUTION_CONTRACT_V1` survive E004/E005 and a historical-retention gate?
3. Does E006 support evidence-sufficiency retrieval locally?
4. How much does an explicit state resolver improve current-state accuracy over the chosen memory backend?
5. Does context isolation reduce drift/rework enough to justify the added structure?
6. Is Ponder materially better than the native ChatGPT Project + Site + Computer History cockpit for governance review?

## Next Run

Run ID: 005
Target: 2026-09-08
Priority: continuity closure > E004/E005/E006 results > E009 > E010 > frontier freshness.

A small freshness scan is allowed, but a full frontier expansion is gated on reducing experiment debt.
