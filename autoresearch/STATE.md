# AutoResearch State

Last updated: 2026-09-22
Timezone: America/Phoenix
Status: canonical Runs 003–005 active on `main`; Run 006 under review; evaluation-isolation recovery remains P0
Canonical repository: `Vvolen/personal_ai_infrastructure`
Latest canonical run: `autoresearch/runs/2026-09-08_run_005.md`
Latest proposed run: `autoresearch/runs/2026-09-22_run_006.md`
Run 006 review branch: `autoresearch/run-006-2026-09-22`

## Continuity Note

Runs 000–002 remain unmaterialized.

Runs 003–005 became canonical history when PR #1 was merged on 2026-09-09 with merge commit `f71c5b501df32c4655e5d96f9a2cb0f454b2e295`.

E003 — Canonical Continuity Writeback: **PASS**.
- GitHub-only recoverability: pass.
- previous-state read without chat reconstruction: pass.
- canonical activation on `main`: pass.

Run 006 discovered that the 2026-09-08 `STATE.md` and `RUN_LEDGER.md` snapshots still described PR #1 as unmerged after the merge occurred. This is now treated as a state-reconciliation failure mode rather than a continuity failure.

## Doctrine Status Boundary

- **Active doctrine** is approved canonical operating policy.
- **Proposed doctrine/amendments** may shape linked experiments but cannot govern their own promotion.
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

**Run 006 amendment candidate — event reconciliation:** canonical state snapshots must be reconciled against fresher authoritative repository events before use. A stale snapshot cannot override merge state, commit ancestry, or other control-plane facts.

### D-AR-005 — Context Is a System
Prompts are one layer of a broader context system: canonical state, evidence, tools, permissions, working context, skills, memory, and compaction.

### D-AR-006 — Tasks Are Triggers, Not Canonical State
Scheduled Tasks are trigger/report surfaces. Every governed run re-reads external canonical state.

Current capability note: supported trigger families now include one-off, recurring, monitoring, and eligible event-triggered Work flows from Gmail, Slack, and GitHub activity. This expands the trigger taxonomy but does not change the authority boundary.

### D-AR-007 — Broad Recall, Narrow Commitment
Retrieval may be exploratory. Durable memory writes must be typed, source-grounded, scoped, reversible, and governed by promotion.

### D-AR-008 — Memory / Context Is a Lifecycle
Design memory around architecting, ingesting, scoping, anticipating, retrieving, compacting/consolidating, and forgetting while preserving provenance.

### D-AR-009 — Task-Specific Harnesses
Prefer versioned harness profiles for materially different task families rather than one monolithic global prompt. Change the narrowest relevant layer first.

### D-AR-010 — Trace + Artifact Evaluation
Evaluate both final artifacts and execution trajectories. A correct answer reached through an invalid process can still be a system failure.

**Run 006 amendment candidate — verification anchoring:** when a grounded or machine-verifiable task-completion signal exists, it is primary for promotion decisions. LLM-judge scores remain auxiliary and should be calibrated against grounded outcomes for the task family.

## Proposed Doctrine — Run 003

### D-AR-011 — Frozen Outer Anchor
Status: proposed; validate through E004/E005 + human review.
Ordinary runs may evolve task harnesses and bounded evolver policies but may not automatically rewrite governance/evidence/safety anchors.

### D-AR-012 — Attribution Before Promotion
Status: proposed; validate through E005 + human review.
High-impact harness changes require evidence that the changed component plausibly caused the gain. For adaptive trajectories, prefer replay, controlled interventions, ablations, leave-one-out, or counterfactual probes over post-hoc trace inspection alone where feasible.

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
Candidate development, held-out execution, evaluator-only expectations, and promotion authority must be separated by enforceable context/tool boundaries.

Minimum requirements:
- development-only evolver context;
- candidate freeze before held-out release;
- held-out runner without evaluator key;
- evaluator only after outputs/traces freeze;
- immutable dataset/version receipt;
- exposure/contamination receipt;
- separate promotion authority.

## Current Reusable Policies

- `autoresearch/policies/HARNESS_EVOLUTION_CONTRACT_V1.md` — proposed; awaits valid E004/E005.
- `autoresearch/policies/STATEFUL_CONTEXT_CONTROL_CONTRACT_V1.md` — proposed; awaits E009/E010.
- `autoresearch/policies/EVALUATION_ISOLATION_AND_PROMOTION_CONTRACT_V1.md` — proposed; validate through E011.
- `autoresearch/policies/STATE_RECONCILIATION_AND_VERIFIABLE_EVAL_CONTRACT_V1.md` — proposed in Run 006; review required.

## Active Hypotheses

### H001 — AutoResearch can upgrade personal AI use
Confidence: medium-high. Governance artifacts are compounding; experimental conversion remains the bottleneck.

### H002 — Doctrine + experiments are the compounding mechanism
Confidence: high. Run 006 closes E003, but substantive evaluation debt remains.

### H003 — GitHub should be control plane; Ponder/Sites/Projects should be interfaces
Confidence: high. E007 remains the comparison.

### H004 — Bounded task-specific harness evolution beats monolithic self-editing
Confidence: medium-high. Needs valid E004.

### H005 — Causal/interventional attribution improves promotion decisions
Confidence: medium. Needs valid E005.

### H006 — Evidence-sufficiency stopping can reduce retrieval cost without quality loss
Confidence: medium-high. Needs valid E006.

### H007 — Supersession resolution materially improves mutable-state memory
Confidence: medium-high. Needs E009.

### H008 — Functional context isolation reduces drift/context cost
Confidence: medium-high. Needs E010.

### H009 — Evaluation isolation is required for credible self-improving harness experiments
Confidence: high as methodology; local runtime utility/cost needs E011.

### H010 — Grounded outcome anchoring reduces false promotion versus judge-only evaluation
Confidence: medium-high from external evidence; test locally through E011-B.

## Active Experiments

### E003 — Canonical continuity writeback
Status: **PASS** after 2026-09-09 merge reconciliation.

### E004 — Bounded task-specific harness evolution
Status: blocked pending E011 isolated evaluator runtime.
Frozen v1 dataset remains intact for an isolated context. Historical-retention slice required.

### E005 — Attribution before promotion
Status: blocked pending E011.

### E006 — Evidence-sufficiency retrieval
Status: blocked pending E011; first real recovery target after E011-A/B.

### E007 — Cognitive cockpit
Status: reframed; contingent on Ponder access.
Compare Ponder with native ChatGPT workspace over identical canonical state, including governed typed-action support.

### E008 — Voice-to-project intake
Status: parked.

### E009 — State-first memory wrapper
Status: proposed/unexecuted.

### E010 — Functional context isolation
Status: proposed/unexecuted.

### E011 — Isolated Evaluation Runner
Status: proposed; P0.

Run 006 subtests:
- E011-A — synthetic isolation-runtime dry run with seeded contamination attempt.
- E011-B — grounded evaluation calibration against objective completion.

No E012+ created.

Full current board: `autoresearch/experiments/2026-09-22_to_2026-10-06.md`.

## Experiment Debt

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
new_experiment_ids_run006: 0
```

## Current Frontier Candidates — Not Doctrine

Queued behind experiment debt:
- discovery-history replay for exploration-policy improvement (Dream-RSI pattern);
- kernel-managed shared memory / centralized injection policy;
- self-evolving retrieval indices;
- procedural graphs and functional memory units;
- matched-replay procedural skill evolution;
- attribute-before-memorize / memory credit assignment;
- context privilege and authority metadata;
- replay-aware forgetting;
- substrate-aware planning;
- typed prospective intention stores;
- repository-to-verified-skill compilation for SOSOG.

Do not assign new D-AR identifiers until linked local evidence or an explicit governance decision justifies expansion.

## Open Questions

1. Can E011-A enforce genuinely separate evaluation contexts with acceptable overhead?
2. How often does judge-only evaluation disagree with grounded completion in our task families?
3. What does a valid E006 result say once E011 exists?
4. Does E009 support supersession-aware state locally, including authority/scope failures?
5. Does E010 reduce drift/rework enough to justify context-plane structure?
6. Is Ponder materially better than native ChatGPT workspace for governed review and typed action?
7. Should GitHub PR-event Tasks run a state-reconciliation check after merges?
8. When enough trajectories exist, can AutoResearch history become a useful replay simulator for exploration-policy optimization?

## Next Run

Run ID: 007
Target: 2026-10-06
Priority: review Run 006 reconciliation > E011-A > E011-B > valid E006 result > E005/E004 > E009 > bounded frontier freshness.

Run 007 remains evaluation-first unless experiment debt is materially reduced.
