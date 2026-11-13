# Replayable Evidence Capsule Contract v1
Date: 2026-11-13. Status: **PROPOSED, NOT ACTIVE**. Linked Run 009V; E011-A2-R.

## Amendment candidate: D-AR-004
An experimental GitHub narrative receipt does not by itself establish independent repeatability. Experiments should retain a versioned, authorized capsule: exact source+hash, fixtures, environment, command, expected output, raw result, protected-data scope and reviewer decision. Protected held-out/evaluator-only E004–E006 contents must **not** be copied into general GitHub; refer to a restricted immutable store and authorized verifier receipt.

## Amendment candidate: D-AR-010
Explicit evidence states: `reported`, `code_recovered`, `replayed`, `independently_reviewed`, `promoted`. Replay verifies a bounded software claim. It does not authenticate source origin, prove independent model contexts, demonstrate real-world task success, or permit an evaluator to promote itself.

## Minimal schema
```yaml
experiment_id:
source_ref:
source_sha256:
runtime_version:
command:
fixtures: []
expected_outputs:
raw_execution_receipts: []
evidence_class: reported | code_recovered | replayed | independently_reviewed | promoted
independent_reviewer:
authorization_scope:
protected_material_locator: null
```

## Empirical observation
Run 009T/009U source ZIPs were replayed in a fresh process Nov 13: 14/14 + 10/10 deterministic tests; 009T historical gate remains NOT_READY; 009U witness remains TRACE_CONSISTENT_NOT_ISOLATION_PROOF. The expected executable GitHub paths returned 404 even though narrative summaries were available. The sources are delivered with the user-local Run 009V ZIP, not claimed uploaded here.

## Release rule
No automatically generated or structurally coherent replay record constitutes E011-A2 PASS. Actual separate contexts, fully verified exposures, precommit, overhead and independent R4 review remain compulsory; only then may E011-B begin precommitment. Neither amendment nor this contract is active until human-reviewed promotion.
