# Belief state and memory validity contract v1

Created: 2026-10-07
Status: proposed; not active doctrine
Linked run: `autoresearch/runs/2026-10-06_run_007.md`
Validation target: E009-A; artifact-binding checks through E011-A2/B

## Scope and authority

Materializes the contract named, but not committed, in Run 007. This is a review proposal written on October 7, not evidence that a policy or runtime existed on October 6.

Extends proposed D-AR-017 and the C1/C3 separation in `autoresearch/policies/STATEFUL_CONTEXT_CONTROL_CONTRACT_V1.md`. Supports the proposed D-AR-010 and D-AR-013 amendments. The outer governance specification, active doctrine, permissions, and human promotion requirements remain unchanged. A validated working belief is still not permission to act or a promoted policy.

## Belief-state record

```yaml
belief_state:
  id:
  version:
  parent_version:
  status: candidate | validated | disputed | invalidated | superseded
  task_scope:
  objective_ref:
  authority_policy_ref:
  environment_version:
  world_state_refs: []
  epistemic_gaps: []
  achievement_gaps: []
  active_gap_ref:
  confidence:
  source_refs: []
  depends_on: []
  valid_from:
  valid_to:
  supersedes: []
  superseded_by: []
  last_verified_at:
  progress:
    last_observable_change:
    repeated_attempts:
    unresolved_contradictions: []
    recovery_trigger:
    next_action:
```

World-state claims reference versioned state records with evidence and per-claim confidence. Gaps have stable IDs, status, evidence needed or completion criteria, and objective relations. An epistemic gap names something unknown; an achievement gap names something undone. Closing either requires linked evidence. A global confidence score cannot erase a disputed claim. An active gap must belong to the recorded objective; changing the objective or authorization requires the existing review boundary.

## Candidate update, validation, commit

1. Read the current version and reconcile authoritative events using `autoresearch/policies/STATE_RECONCILIATION_AND_VERIFIABLE_EVAL_CONTRACT_V1.md`.
2. Propose a delta against that exact parent version. Include the actor, time, affected claims/gaps, evidence, expected change, and rollback pointer. Keep the previous record and source material intact.
3. Validate required fields, source availability, task scope, authority, supersession and dependency consistency, environment validity, and gap completion evidence. Use deterministic checks where possible; label model judgments and unresolved uncertainty.
4. Return `accept`, `reject`, or `needs_evidence` with reasons. Missing evidence, unresolved authority conflicts, and dependency cycles cannot yield `accept`. A sentinel validates evidence; it cannot grant itself promotion authority.
5. Commit an accepted working-state version only if the parent version is still current. Otherwise rebase the proposal and validate again. Record before/after hashes and the validation receipt. Persist governance or policy changes only through the existing human review process.

Rejected and unresolved updates remain inspectable proposals. Never overwrite a source record to make it agree with a newer belief.

## Memory validity at read time

For each recalled item:

1. Resolve source identity, version, authority, scope, validity interval, supersession, and dependencies.
2. Compare the item's environment assumptions with the current repository commit, configuration, permissions, and relevant authoritative events. A timestamp alone does not establish validity.
3. Emit a receipt with item/source hash, observed environment version, checks performed, check time, reasons, and outcome: `valid`, `stale`, `conflicting`, or `unknown`.
4. Only `valid` evidence can support a current factual assertion. Preserve other items as historical evidence or an explicit uncertainty; seek fresh evidence before dependent action. If the relevant environment changes before action, validate again.

Invalidating a source invalidates or disputes dependent beliefs and derived summaries until rechecked. It does not delete the source. Do not invalidate unrelated claims merely because they share a document or author. No-memory and unavailable-source cases remain `unknown`, never inferred success.

## Progress and recovery

Before execution, the task profile records observable progress criteria, a repeat/no-progress trigger, and an allowed recovery action. Trigger on repeated unchanged state, reopened gaps, contradictory evidence, or repeated failure of the same approach. Record why progress is judged stalled.

Recovery may re-check an assumption, gather missing evidence, try a documented alternative, or request a decision. It cannot silently change the objective, permissions, evaluation thresholds, or promotion rules. Preserve failed branches and the evidence that caused recovery.

## Negative knowledge

Store a failed route, counterexample, or invalidated assumption with its own ID, tested claim, conditions/environment, source/trace references, result, confidence, dependencies, and validity interval. Distinguish a demonstrated counterexample from an unexecuted idea or missing evidence. Retrieve it only for matching conditions and revalidate when those conditions change. A failed method in one setting is not a universal prohibition.

## Multi-agent merge rules

Workers return structured proposals against a named parent version; raw traces stay in execution scratch. A designated state writer checks evidence and dependencies and commits one validated version at a time. Duplicate claims can share provenance; conflicting claims remain disputed until authority/evidence resolves them. Never select truth by arrival time, model confidence, or majority vote alone. Stale-parent updates require revalidation; preserve each worker's attribution and rejected proposals.

## Artifact-bound evaluation

A consequential result receipt binds candidate commit/hash, baseline, dataset/split hashes, frozen output/trace hashes, verifier and judge versions, environment/tool configuration hashes, exposure receipt, evaluator identity, decision, and reviewer identity/time. A changed candidate requires fresh applicable evaluation; evidence for candidate A cannot authorize candidate B.

Use `autoresearch/policies/EVALUATION_ISOLATION_AND_PROMOTION_CONTRACT_V1.md` for role isolation and `autoresearch/evaluations/E011_B_PRECOMMITMENT_V1.md` for grounded-evaluation precommitment. A working-belief validation receipt is not an experiment PASS or a human promotion decision.

## Validation and adoption

E009-A compares historical retrieval with belief-state plus supersession/read-time validation on at least 24 mutable-state cases. Include stale evidence, conflicting authority, changed environments, unavailable sources, dependent invalidation, concurrent stale-parent updates, and valid evidence that should survive. Measure current-state accuracy, stale-evidence leakage, task completion, token cost, false invalidation, and recovery. Freeze cases, metrics, and acceptance criteria before execution under the current experiment board.

This document defines a proposed contract. It implements no memory service, sentinel runtime, or experiment. Adoption requires linked valid results, review of limitations and rollback, and a recorded human decision under existing governance. No experiment result or policy promotion is claimed by adding this file.
