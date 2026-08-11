# Harness Evolution Contract v1

Created: 2026-08-11
Status: proposed
Owner: AutoResearch governance loop

## Purpose

Allow task-specific agent harnesses to improve from evidence without allowing an ordinary research run to silently rewrite the governance layer that judges those improvements.

The contract separates four layers:

```text
L0  Frozen outer anchor
    governance, evidence taxonomy, source hierarchy, write permissions,
    acceptance criteria, safety boundaries, audit requirements, rollback rules

L1  Evolver policy
    proposes bounded changes to task harnesses and chooses search strategy

L2  Task harness profile
    context assembly, tools, memory scope, orchestration, permissions,
    stop rules, output schema, task-specific evaluators

L3  Working state
    ephemeral context, scratch files, retrieved evidence, trajectories
```

## Core rule

An ordinary AutoResearch run may propose or test changes to L1 and L2. It may not automatically modify L0. Changes to L0 require an explicit governance audit and human review.

## Change record

Every harness modification must be represented as a falsifiable record:

```yaml
change_id:
run_id:
task_family:
baseline_profile_version:
candidate_profile_version:
target_layer: L1 | L2
target_component: context | tools | memory | orchestration | permissions | stop_rule | output | evaluator
hypothesis:
minimal_diff:
expected_causal_mechanism:

experiment:
  development_cases: []
  held_out_cases: []
  model_snapshot:
  environment_manifest_hash:
  tool_manifest_hash:
  evaluator_version:

trajectory_attribution:
  suspected_component:
  evidence:
  perturbation_or_ablation:
  confidence:

results:
  baseline_metrics: {}
  candidate_metrics: {}
  cost_delta:
  latency_delta:
  protected_regressions: {}
  security_exposure_delta:

decision:
  status: propose | promote | reject | retest | rollback
  reason:
  rollback_pointer:
  negative_result_preserved: true
```

## Promotion gates

A candidate can be promoted only when all applicable gates pass:

1. The exact component and minimal diff are recorded.
2. The expected causal mechanism is stated before evaluation.
3. Development cases show an improvement above a predefined minimum effect.
4. Held-out artifact quality does not regress beyond tolerance.
5. Trajectory evidence supports the changed component as a plausible cause of the improvement; final score alone is insufficient for high-impact changes.
6. No L0 governance invariant is weakened.
7. The change has a rollback pointer.
8. Cost, latency, and security exposure are measured where relevant.
9. Negative and null results are preserved.
10. The new profile receives a version identifier and evaluation tuple.

## Evaluation tuple

Every score attached to a harness must include:

```yaml
benchmark_version:
harness_profile_id:
harness_profile_version:
environment_manifest_hash:
model_snapshot:
tool_manifest_hash:
evaluator_version:
dataset_split:
```

Scores without this tuple are not comparable across runs.

## Context and memory contract

Each task harness profile must declare:

```yaml
context:
  always_load: []
  retrieve_on_demand: []
  budget_tokens:
  compaction_policy:
  compaction_validator:

retrieval:
  source_hierarchy: []
  lexical_enabled:
  semantic_enabled:
  graph_enabled:
  evidence_sufficiency_threshold:
  escalation_rule:
  stop_rule:

memory:
  readable_layers: []
  candidate_write_layers: []
  direct_write_layers: []
  provenance_required: true
  stale_after:
  promotion_gate:
```

The design principle is broad discovery but narrow commitment: retrieval can explore; durable memory writes must be typed, source-grounded, scoped, and reversible.

## Harness security policy

Treat the harness itself as an attack and IP surface.

- Never place secrets in prompts or shareable harness text.
- External agents receive the capabilities and constraints they require, not the complete internal evolution policy.
- Prefer profile IDs and scoped interfaces over copying full private harness specifications into third-party contexts.
- Log which harness components are exposed to external systems.
- Evaluate behavioral leakage when a valuable harness is repeatedly accessible through black-box interactions.
- Security-sensitive changes require adversarial evaluation before promotion.

## Outer-anchor invariants

The following remain frozen during ordinary AutoResearch runs:

- Fact / Inference / Speculation / Recommendation taxonomy.
- GitHub or an explicitly designated ledger as canonical governance state.
- Source provenance for load-bearing claims.
- Human-review requirement for governance-layer changes.
- Preservation of negative results and decision traces.
- Bounded permissions and rollback paths.
- No doctrine promotion from an unvalidated single observation.

## Relationship to Ponder, Sites, and other cognitive workspaces

Human-facing workspaces are projections of governed state, not the authority for it.

A Ponder Cognitive Artifact or ChatGPT Site may render the source graph, hypotheses, proposed diffs, experiment status, and decision queue. Approved changes must still write back to the canonical state layer through the same promotion contract.

## Reference evidence

- Tailin Zhou, "Hierarchical Self-Improvement: A Framework for Task-Specific Evolvable Agent Harnesses," arXiv:2608.08466, 2026-08-09. https://arxiv.org/abs/2608.08466
- Jing Chen et al., "Long-Horizon Agent Trajectory Attribution," arXiv:2608.06909, 2026-08-07. https://arxiv.org/abs/2608.06909
- Yu Cui et al., "Agent Harness Distillation," arXiv:2607.28147, 2026-07-30. https://arxiv.org/abs/2607.28147
- Gaurav Dadhich, "Agentic Context Management," arXiv:2607.21503, 2026-07-23. https://arxiv.org/abs/2607.21503
