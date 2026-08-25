# Stateful Context Control Contract v1

Created: 2026-08-25
Status: proposed
Linked run: `autoresearch/runs/2026-08-25_run_004.md`

## Purpose

Define a backend-agnostic control layer for long-horizon agent memory and context. The contract separates canonical current state, historical evidence, task planning state, execution scratch, and ambient recall so that a memory backend does not silently become the authority for truth.

## 1. State record schema

Mutable facts, constraints, decisions, plans, and preferences must be able to represent revision.

```yaml
state_record:
  id:
  entity_or_scope:
  type: fact | constraint | decision | plan | preference | hypothesis | policy
  value:
  status: current | superseded | disputed | invalidated | candidate
  valid_from:
  valid_to:
  supersedes: []
  superseded_by: []
  depends_on: []
  source_refs: []
  confidence:
  created_at:
  last_verified_at:
  owner:
```

A retrieval hit is not automatically current state.

## 2. Context planes

### C0 — Governance / identity

Stable rules, authorization boundaries, evidence taxonomy, permissions, and acceptance criteria.

Properties:
- smallest plane
- highest protection
- explicit version
- ordinary task runs cannot rewrite it

### C1 — Objective / plan state

Current objective, done state, active constraints, chosen strategy, decisions, open loops, and next action.

Properties:
- compact
- revision-aware
- optimized for continuing the task
- accepts structured handoffs, not raw traces

### C2 — Execution scratch

Tool outputs, intermediate reasoning artifacts, subagent traces, temporary transforms, failed attempts.

Properties:
- large and disposable
- can be compacted aggressively
- cannot silently update C1

### C3 — Evidence / provenance

Source spans, retrieved documents, measurements, citations, contradictory evidence, confidence.

Properties:
- source recoverable
- append-friendly
- supports contradiction and supersession analysis

### C4 — Ambient reinstatement

Computer History, local activity cues, chat-history recall, recent-app context, temporal hints.

Properties:
- useful for finding where work happened
- non-authoritative
- never sufficient alone for durable state promotion

## 3. Read pipeline

```text
objective
  ↓
resolve current C1 state
  ↓
retrieve relevant C3 evidence / historical state
  ↓
apply supersession resolution
  ↓
route to task-appropriate memory substrate
  ↓
assemble bounded working context
  ↓
execute
```

Current-state resolution happens before broad historical context is allowed to influence action.

## 4. Write pipeline

```text
candidate observation
    ↓
source/provenance check
    ↓
dedupe/entity resolution
    ↓
supersession/conflict analysis
    ↓
promotion gate
    ↓
durable write
    ↓
derived-index / graph / wiki update
```

No automatic summary may overwrite a more specific source-grounded record.

## 5. Memory substrate routing

A harness profile must declare memory strategy by task regime.

```yaml
memory_route:
  task_family:
  horizon:
  decision_sensitivity:
  preferred_substrates: []
  retrieval_depth:
  broad_recall_allowed:
  action_context_priority:
  current_state_resolution_required: true
```

Examples:
- factual synthesis may favor broader retrieval;
- sequential action tasks may prioritize compact action-critical state;
- temporal decision tasks require supersession resolution;
- relationship-heavy analysis may add graph traversal;
- exact-source work requires lexical/source-span retrieval.

## 6. Context isolation / handoff

A specialist subagent returns:

```yaml
handoff:
  task:
  status:
  result:
  decisions_proposed: []
  evidence_refs: []
  unresolved_gaps: []
  state_changes_proposed: []
  execution_artifacts: []
```

The orchestrator decides what enters C1. Raw subagent traces remain C2 unless explicitly promoted.

## 7. Harness retention gate

Every candidate harness update records:

```yaml
retention:
  current_task_gain:
  historical_suite:
  previously_passing_cases:
  newly_regressed_cases:
  capability_forgetting_rate:
  accepted_regression_budget:
```

A candidate cannot be promoted only because it improves current tasks.

## 8. Causal evaluation rule

For high-impact adaptive trajectories:

1. record the targeted component before the test;
2. preserve baseline and candidate traces;
3. use held-out outcomes;
4. use replay, ablation, leave-one-out, or intervention when feasible;
5. report causal confidence, not just score delta.

Post-hoc trace inspection alone is not sufficient when downstream behavior can adapt to an earlier error.

## 9. Online drift state

Long-running roles may maintain a lightweight authorization monitor:

```yaml
authorization_state:
  authorized_role:
  authorized_goal:
  accepted_evidence_scope:
  current_role:
  current_goal:
  evidence_origin:
  drift_score:
  escalation_required:
```

The monitor should be deterministic after structured extraction where practical.

## 10. Interface-state separation

Ponder, ChatGPT Sites, Projects, dashboards, and similar workspaces may render and edit *proposals* over this state.

They do not become the authority merely because they are easier to inspect.

Approved changes round-trip to the canonical ledger with:
- actor
- timestamp
- prior version
- new version
- evidence/decision reference
- rollback pointer

## 11. Experiment debt fields

Every experiment queue exposes:

```yaml
experiment_debt:
  proposed:
  running:
  completed:
  promoted:
  rejected:
  parked:
  stale:
  median_age_days:
  oldest_open_days:
```

A run should not create an unbounded number of new experiments while old P0 tests remain unresolved.

## 12. Minimum implementation sequence

1. Add supersession fields to the canonical state schema.
2. Separate C1 plan state from C2 execution scratch in one real workflow.
3. Add historical-retention cases to harness promotion.
4. Add experiment-debt metrics to the ledger.
5. Only then evaluate more sophisticated graph/memory substrate routing.

## References

- https://arxiv.org/abs/2608.19652
- https://arxiv.org/abs/2608.15008
- https://arxiv.org/abs/2608.15703
- https://arxiv.org/abs/2608.19013
- https://arxiv.org/abs/2608.20627
- https://arxiv.org/abs/2608.17718
