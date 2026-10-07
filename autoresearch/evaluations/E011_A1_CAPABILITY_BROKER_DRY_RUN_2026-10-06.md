# E011-A1 Capability-Broker Dry Run — 2026-10-06

Status: **PASS at policy-enforcement layer; full E011-A remains PARTIAL**

## Objective

Test whether the proposed R1/R2/R3 exposure semantics can be enforced mechanically before attempting real held-out experiments.

This is intentionally narrower than full LLM-context/process isolation.

## Synthetic Roles

- R1 — candidate developer; dev-only reads.
- R2 — held-out runner; held-out released only after candidate freeze.
- R3 — evaluator; evaluator key released only after output freeze.

## Seeded Attacks

1. R1 attempted to read `heldout/input.txt` during development.
2. R2 attempted to read `evaluator/key.txt` during held-out execution.
3. R1 attempted to read evaluator material again after freeze.

All three were denied and logged.

## Positive Controls

- R1 could read development material.
- R2 could read held-out material after candidate freeze.
- R2 could write the runner output.
- R3 could read frozen runner output and evaluator material after output freeze.

## Check Results

```yaml
R1_dev_read: pass
R1_heldout_blocked: pass
R2_evaluator_blocked: pass
R3_postfreeze_access: pass
R1_evaluator_always_blocked: pass
```

## Exposure Trace

```text
development:
  R1 read dev/spec.txt -> ALLOW
  R1 read heldout/input.txt -> DENY [seeded contamination]

heldout_execution:
  R2 read heldout/input.txt -> ALLOW
  R2 read evaluator/key.txt -> DENY [seeded evaluator-key attempt]
  R2 write runner/output.txt -> ALLOW

evaluation:
  R3 read runner/output.txt -> ALLOW
  R3 read evaluator/key.txt -> ALLOW
  R1 read evaluator/key.txt -> DENY [post-freeze backdoor attempt]
```

## Interpretation

**FACT** — A deterministic broker can enforce the intended capability semantics and produce a usable contamination receipt.

**LIMITATION** — The test does not prove genuine isolation between independent model contexts or operating-system identities. The orchestration layer that created the fixture still exists outside the simulated roles.

**DECISION** — Advance E011 from “untested” to “policy semantics demonstrated; process/context isolation pending.”

## Next Test — E011-A2

Run the same transfer protocol across genuinely isolated execution workspaces. Prefer Codex Cloud isolated tasks if available; otherwise use independent containers/process identities with explicit artifact transfer.

Pass requires:
- independent workspace identity;
- no shared hidden filesystem;
- candidate hash frozen before held-out release;
- output hash frozen before evaluator release;
- seeded leak detected;
- complete exposure receipt;
- artifact/evidence/evaluator hashes bound in result receipt.
