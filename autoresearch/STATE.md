# AutoResearch State

Last updated: 2026-08-11
Timezone: America/Phoenix
Status: active — continuity recovery
Canonical repository: `Vvolen/personal_ai_infrastructure`
Latest proposed run: `autoresearch/runs/2026-08-11_run_003.md`

## Continuity Note

The original bootstrap state and governance files were committed in June 2026, but `autoresearch/runs/` was never materialized on `main`. Runs 000-002 therefore have no canonical GitHub artifacts or evaluation results.

Useful scheduled research may have existed outside GitHub, but external/chat-only outputs are non-canonical until explicitly backfilled. Run 003 is the first run designed to close the loop through a reviewable GitHub branch/PR containing the run artifact, state compaction, ledger update, reusable policy, and experiments.

## Doctrine Status Boundary

This system exists to compound the user's AI operating system through governed research, experiments, and behavior change. It is not an AI-news digest.

- **Active doctrine** is approved canonical operating policy and may govern ordinary runs.
- **Proposed doctrine** is a versioned candidate for evaluation. It may inform an experiment, but it must not be treated as an active rule, used to justify its own promotion, or silently folded into active doctrine.
- Promotion from proposed to active requires the linked validation evidence, a recorded decision, and human review. Until then, a future run reading only this file must preserve the boundary.

## Active Doctrine

### D-AR-001 — Prior State First
Every run reads canonical prior state before frontier research.

### D-AR-002 — Epistemic Separation
Load-bearing claims are distinguished as Fact, Inference, Speculation, or Recommendation.

### D-AR-003 — Behavior Change, Not Notes
A run is incomplete unless it produces a reusable artifact, evaluated change, or falsifiable experiment that can affect future behavior.

### D-AR-004 — GitHub as Governance Control Plane
GitHub or an explicitly superseding ledger is the authority for doctrine, policies, run history, and versioned decisions. Ambient/chat memory is supporting recall, not mandatory state.

### D-AR-005 — Context Is a System
Prompts are one layer of a broader context system including canonical state, retrieved evidence, tool results, permissions, working context, skills, memory, and compaction.

### D-AR-006 — Tasks Are Triggers, Not Canonical State
Scheduled Tasks are appropriate for cadence, reminders, monitoring, and delivery. Every governed run re-reads external canonical state; task history alone is insufficient.

### D-AR-007 — Broad Recall, Narrow Commitment
Retrieval may be exploratory. Durable memory writes must be typed, source-grounded, scoped, reversible, and governed by a promotion rule.

### D-AR-008 — Memory / Context Is a Lifecycle
Design memory around architecting, ingesting, scoping, anticipating, retrieving, compacting/consolidating, and forgetting while preserving provenance. A memory store alone is not a memory architecture.

### D-AR-009 — Task-Specific Harnesses
Prefer versioned harness profiles for materially different task families rather than one monolithic global prompt. Change the narrowest relevant layer first.

### D-AR-010 — Trace + Artifact Evaluation
Evaluate both the final artifact and the execution trajectory. A correct answer reached through an invalid process can still be a system failure.

## Proposed Doctrine

The following entries originated in Run 003 and remain non-authoritative pending their stated validation and a separate promotion decision.

### D-AR-011 — Frozen Outer Anchor
Status: proposed; validate through E004/E005 and human review.

Ordinary AutoResearch runs may evolve task harnesses and bounded evolver policies but may not automatically rewrite the governance/evidence/safety anchor. Governance changes require a dedicated audit and human review.

### D-AR-012 — Attribution Before Promotion
Status: proposed; validate through E005 and human review.

High-impact harness changes require evidence that the changed component plausibly caused the gain. Use controlled A/Bs, ablations, leave-one-out tests, or trajectory attribution where feasible.

### D-AR-013 — Interface-State Separation
Status: proposed; validate through E007 and human review.

Ponder Cognitive Artifacts, ChatGPT Sites, dashboards, and similar cognitive workspaces are human-facing projections over canonical state, not the authority for that state.

### D-AR-014 — Harness Exposure Policy
Status: proposed; validate through E004 security-exposure measurement, E005-H02, and human review.

Treat valuable harness logic, evolution policy, and evaluator design as scoped security/IP surfaces. External runtimes receive only the behavior, capabilities, and constraints they require.

### D-AR-015 — Evidence-Sufficiency Retrieval
Status: proposed; validate through E006 and human review.

Use fixed retrieval budgets as hard safety caps, not mandatory quotas. Stop earlier when evidence support, source authority, freshness, independent coverage, and contradiction checks are sufficient; escalate only when expected evidence gain justifies cost.

## Proposed Operating Principles

Status: proposed; these Run 003 heuristics may shape the linked experiments but are not active doctrine or promotion criteria until separately reviewed and promoted.

- Standing-on-the-shoulders-of-giants research: prefer primary work, production engineering, and frontier practitioners before invention.
- Retrieval should begin cheap and precise and escalate progressively.
- Preserve source provenance through memory consolidation and context compaction.
- Convert repeated failures into changes to harness, retrieval, evaluator, memory, or stop policy.
- Keep the governance anchor harder to change than task-level behavior.
- Preserve negative/null experiment results and rollback information.
- Score comparisons require a versioned evaluation tuple: benchmark, harness, environment, model, tools, evaluator, dataset split.
- Ponder/Sites can become cognitive cockpits; approved decisions must write back to canonical state.

## Active Hypotheses

### H001 — AutoResearch can upgrade personal AI use
Status: active
Confidence: medium-high
Evidence state: strong architecture rationale, insufficient longitudinal local measurement.
Next action: measure behavior-change conversion and continuity over the next 2-3 runs.

### H002 — Doctrine + experiments are the core compounding mechanism
Status: active
Confidence: high
Next action: require explicit trial-to-behavior conversion on the next run before new research.

### H003 — GitHub should be control plane; Ponder/Sites should be interfaces
Status: active
Confidence: high
Reason: current product evolution strengthens the separation between interactive workspaces and auditable canonical state.
Next action: E007 cognitive-cockpit A/B.

### H004 — Bounded task-specific harness evolution beats monolithic self-editing
Status: active
Confidence: medium-high
Next action: E004 with one `frontier_scan` profile and held-out evaluation.

### H005 — Causal trajectory attribution improves harness promotion decisions
Status: active
Confidence: medium
Next action: E005 seeded-trajectory test.

### H006 — Evidence-sufficiency stopping can reduce retrieval cost without quality loss
Status: active
Confidence: medium-high
Next action: E006 fixed-budget vs sufficiency-gated retrieval.

## Active Experiments

### E003 — Canonical continuity writeback
Goal: next run can recover complete state from GitHub only.
Status: running pending PR review/merge.
Success: all required state + latest run + experiment artifacts resolve without chat reconstruction.

### E004 — Bounded task-specific harness evolution
Goal: test a mutable `frontier_scan` harness under frozen governance.
Status: proposed

### E005 — Attribution before promotion
Goal: compare final-score-only promotion with component/trajectory attribution.
Status: proposed

### E006 — Evidence-sufficiency retrieval stop rule
Goal: reduce retrieval cost without support/contradiction-quality loss.
Status: proposed

### E007 — Ponder vs ChatGPT Site cognitive cockpit
Goal: compare review efficiency while preserving GitHub as canonical state.
Status: proposed; contingent on Ponder access.

### E008 — Voice-to-project intake contract
Goal: test spoken intake compiled into a typed objective artifact.
Status: proposed

Full experiment definitions: `autoresearch/experiments/2026-08-11_to_2026-08-25.md`.

## Current Evaluation Rubric

Score each run 1-5 on:
- Novelty
- Actionability
- Evidence quality
- Doctrine improvement
- Compounding value
- Integration readiness

Additionally record:
- state continuity
- primary-source coverage
- unsupported-claim count
- trajectory defects when available
- behavior changes promoted/rejected

A run fails if it only summarizes information without changing the operating system or creating an evaluated path to change it.

## Open Questions

1. Does `HARNESS_EVOLUTION_CONTRACT_V1` survive E004/E005 and deserve active-policy status?
2. What evidence-sufficiency scoring function is simple enough to operate yet strong enough to replace fixed source quotas?
3. Is Ponder materially better than ChatGPT Sites for source/claim/experiment review, or is one cockpit enough?
4. Should Workspace Agents be incorporated at all for the personal AI OS, given eligibility boundaries and current API-trigger observability limits?
5. How should non-canonical scheduled outputs from July be archived or ignored without contaminating run history?
6. What minimal workstation/state artifact gives long-running Hermes roles reliable recovery without creating file sprawl?

## Next Run

Run ID: 004
Target: 2026-08-25
First action: evaluate E003-E008 and perform trial-to-behavior conversion before any new frontier scan.
Priority: continuity > evaluation results > doctrine promotion > new research.
