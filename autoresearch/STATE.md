# AutoResearch State

Last updated: 2026-09-08
Timezone: America/Phoenix
Status: active review branch — continuity recovery + evaluation isolation
Canonical repository: `Vvolen/personal_ai_infrastructure`
Latest proposed run: `autoresearch/runs/2026-09-08_run_005.md`
Review branch: `autoresearch/run-003-2026-08-11`
Review PR: `#1`

## Continuity Note

Runs 000-002 remain unmaterialized. Runs 003-005 are recoverable from GitHub on the review branch/PR, but the PR remains unmerged. `main` therefore still contains the June bootstrap state and does not activate these proposed state changes.

E003 remains a partial pass:
- GitHub-only recoverability: pass.
- previous-state read without chat reconstruction: pass.
- canonical activation: pending human merge/reject/supersede decision.

## Doctrine Status Boundary

- **Active doctrine** is approved canonical operating policy within this review history.
- **Proposed doctrine** may shape linked experiments but cannot govern its own promotion.
- Promotion requires linked validation evidence, a recorded decision, and human review where required by L0.

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
Scheduled Tasks are trigger/report surfaces. Every governed run re-reads external canonical state.

**2026-09-08 capability amendment candidate:** OpenAI now supports one-off, recurring, monitoring, and eligible event-triggered Work tasks from Gmail, Slack, and GitHub events. This expands the trigger taxonomy but does not change the authority boundary.

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

Run 004 amendment candidate remains: for adaptive trajectories, post-hoc trace inspection is not sufficient alone; use replay, controlled interventions, ablations, leave-one-out, or counterfactual probes where feasible.

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
Status: proposed; validate through operating behavior + human review.

Before creating new doctrine candidates or more than two new experiments, each run must resolve, execute, explicitly park, block, or fail prior P0 experiments and record experiment-debt metrics.

### D-AR-017 — Supersession-Aware State
Status: proposed; validate through E009 + human review.

Durable state for mutable facts, constraints, decisions, plans, and preferences must represent revision semantics and resolve current state before historical recall influences action.

Minimum fields: `valid_from`, `valid_to`, `supersedes`, `superseded_by`, `depends_on`, `status`, `source_refs`.

### D-AR-018 — Functional Context Isolation
Status: proposed; validate through E010 + human review.

Long-horizon agents should separate governance/identity, objective/plan state, execution scratch, evidence/provenance, and ambient/history cues. Subtask traces do not automatically enter persistent plan state.

## Proposed Doctrine — Run 005

### D-AR-019 — Evaluation Isolation Boundary
Status: proposed; validate through E011 + human review.

Candidate development, held-out execution, evaluator-only expectations, and promotion authority must be separated by enforceable context/tool boundaries. A held-out claim is invalid when candidate development has already observed the held-out stimulus or evaluator key, even if the agent is instructed to ignore it.

Minimum requirements:
- development-only evolver context;
- candidate freeze before held-out release;
- held-out runner without evaluator key;
- evaluator only after outputs/traces freeze;
- immutable dataset/version receipt;
- exposure/contamination receipt;
- separate promotion authority.

## Current Reusable Policies

- `autoresearch/policies/HARNESS_EVOLUTION_CONTRACT_V1.md` — proposed; awaits valid E004/E005 execution.
- `autoresearch/policies/STATEFUL_CONTEXT_CONTROL_CONTRACT_V1.md` — proposed; awaits E009/E010.
- `autoresearch/policies/EVALUATION_ISOLATION_AND_PROMOTION_CONTRACT_V1.md` — proposed; validate through E011.

## Active Hypotheses

### H001 — AutoResearch can upgrade personal AI use
Confidence: medium-high. The governance artifacts are compounding, but local experimental conversion remains weak.

### H002 — Doctrine + experiments are the compounding mechanism
Confidence: high. Current bottleneck is experiment execution validity.

### H003 — GitHub should be control plane; Ponder/Sites/Projects should be interfaces
Confidence: high. E007 compares human-facing surfaces over identical GitHub state.

### H004 — Bounded task-specific harness evolution beats monolithic self-editing
Confidence: medium-high. Needs valid E004 execution.

### H005 — Causal/interventional attribution improves harness promotion decisions
Confidence: medium. Needs valid E005 execution.

### H006 — Evidence-sufficiency stopping can reduce retrieval cost without quality loss
Confidence: medium-high. Needs valid E006 execution.

### H007 — Supersession resolution materially improves mutable-state memory
Confidence: medium-high from external evidence; E009 required.

### H008 — Functional context isolation reduces drift/context cost
Confidence: medium-high from external evidence; E010 required.

### H009 — Evaluation isolation is required for credible self-improving harness experiments
Confidence: high as a methodological requirement; local implementation utility/cost needs E011.

## Active Experiments

### E003 — Canonical continuity writeback
Status: partial pass.
Recoverability succeeded; activation awaits human PR decision.

### E004 — Bounded task-specific harness evolution
Status: blocked pending isolated evaluator runtime.
Frozen v1 dataset remains intact. The 2026-09-08 AutoResearch context has seen held-out prompts and cannot serve as blind evolver/runner.
Historical-retention slice still required.

### E005 — Attribution before promotion
Status: blocked pending isolated evaluator runtime.
Frozen v1 dataset remains intact. Evaluator-only expectations have been exposed to the current governance context.

### E006 — Evidence-sufficiency retrieval
Status: blocked pending isolated evaluator runtime.
Preferred first recovery experiment under E011.

### E007 — Cognitive cockpit
Status: reframed; contingent on Ponder access.
Compare Ponder with native ChatGPT workspace over identical canonical state; measure both review quality and governed typed-action support.

### E008 — Voice-to-project intake
Status: parked.

### E009 — State-first memory wrapper
Status: proposed.

### E010 — Functional context isolation
Status: proposed.

### E011 — Isolated Evaluation Runner
Status: proposed; P0.

Goal: instantiate separate evolver / held-out runner / evaluator / promoter roles with explicit read/write boundaries and exposure receipts, then produce at least two valid E004-E006 result artifacts.

Full current board: `autoresearch/experiments/2026-09-08_to_2026-09-22.md`.

## Experiment Debt

```yaml
prior_experiments_e003_e010: 8
partial_results: 1
completed_result_artifacts: 0
blocked_pending_isolated_runtime: 3
reframed: 1
parked: 1
proposed_unexecuted: 2
new_experiments_run005: 1
```

## Current Frontier Candidates — Not Doctrine

Run 005 surfaced several mechanisms that remain queued behind experiment debt:

- attribute-before-memorize / memory credit assignment;
- context privilege and authorization scope metadata;
- replay-aware forgetting for derived execution state;
- substrate-aware planning constraints;
- typed prospective intention stores;
- repository-to-verified-skill compilation for SOSOG.

Do not assign new D-AR identifiers until linked local evidence or an explicit governance decision justifies expansion.

## Open Questions

1. Will PR #1 be merged, rejected, or superseded?
2. Can E011 enforce genuinely separate evaluation contexts with acceptable overhead?
3. What do valid E006/E005/E004 results actually say once evaluation isolation exists?
4. Does E009 support supersession-aware state locally, including authority/scope failures?
5. Does E010 reduce drift/rework enough to justify context-plane structure?
6. Is Ponder materially better than the native ChatGPT workspace for governed review and typed action?
7. Can GitHub PR event-triggered Tasks shorten review latency without becoming an authority bypass?

## Next Run

Run ID: 006
Target: 2026-09-22
Priority: human continuity closure > E011 > two valid E004-E006 result artifacts > E009 > bounded frontier freshness.

Run 006 remains evaluation-first unless experiment debt is materially reduced.
