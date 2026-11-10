# Execution Witness and Harness Fingerprint Contract v1
Created 2026-11-10. Status: **PROPOSED, NOT ACTIVE**. Linked run 009U; existing E011-A2-W.

## Why
A candidate digest is not an entire harness. Record the effective model/build, system prompt digest, tool/policy manifest digests, runtime image, repo commit, role/context/workspace identities and active context checkpoint at each consequential boundary. Check drift within a run.

## Proposed D-AR-010 amendment
Bind grounded evaluation to precise candidate/output artifacts **and** effective harness configuration/version, environment, verifier and reviewer evidence. Configuration changes require a trace event, and may invalidate comparisons.

## Proposed D-AR-019 clarification
Witness-chain consistency is necessary evidence-integrity checking, not proof that roles occupied separate model contexts or that a host truly prevented reads. Require real role isolation, complete exposure evidence, negative probes, frozen handoff hashes, independently stored anchoring, overhead measures and independent review before admission.

## Proposed D-AR-018 clarification
Checkpoint, reset and rehydration become typed context transitions with source/provenance, valid active goals and scopes; evaluate benefits against a matched baseline in E010.

## Example witness
```yaml
precommit: {attempt_id:, repo_commit:, roles:, model_and_harness_digest:, expected_probes: []}
events:
  - candidate.freeze
  - forbidden_heldout_read_probe.DENY
  - heldout.release_to_R2
  - output.freeze
  - forbidden_evaluator_read_probe.DENY
  - evaluator.release_to_R3
  - output_bound_verdict
external_precommit_anchor:
external_trace_root_anchor:
review: {independent_reviewer:, evidence_refs:, decision:}
```

A mutable local anchor is *not independently trusted*. A syntactically complete log is not self-authenticating. No linter may emit full E011-A2 PASS or release E011-B.

## Sources
https://arxiv.org/abs/2610.40917
https://arxiv.org/abs/2610.40350
https://arxiv.org/abs/2610.02488

No automatic adoption or merge.
