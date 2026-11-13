# E011-A2 Evidence-Admission Gate v1

Created: 2026-11-07 | Status: **PROPOSED, NOT ACTIVE** | Linked run: 009T | Existing experiment: E011-A2

## Proposed D-AR-019 amendment
A release-gating experiment requires a versioned, independently reviewable admission manifest. It must precommit identities, frozen input/candidate/output and evaluator-key release ordering, read scopes, exposure logs, denied negative probes, comparable overhead and independent reviewer identity/decision. The **existence of fields** is never proof that claims are true. Structural readiness may only mean **READY_FOR_EXTERNAL_VERIFICATION**. Only a separate independent review of externally grounded evidence can establish A2 PASS.

## Proposed D-AR-010 amendment
Absent, unknown or unverified evidence remains **NOT_READY** or **INCONCLUSIVE**; a limited policy or DAC PASS is never upgraded to full runtime isolation. Bind claims to precise candidate/environment/attempt/verifier and retain negative results.

## Machine-checkable structural fields
```yaml
experiment_id: E011-A2
attempt_id:
environment: {image_digest:, repo_commit:, isolation_backend:}
precommit: {commit_sha:, manifest_sha256:, created_at:}
roles:
  R1: {principal_id:, context_id:, workspace_id:, allowed_reads: []}
  R2: {principal_id:, context_id:, workspace_id:, allowed_reads: []}
  R3: {principal_id:, context_id:, workspace_id:, allowed_reads: []}
candidate: {sha256:, frozen_at:}
heldout: {released_at:}
output: {sha256:, frozen_at:}
evaluator_key: {released_at:}
transfers:
  candidate: {sha256:, authorized_by:, receipt_id:}
  output: {sha256:, authorized_by:, receipt_id:}
exposure: {logging_complete:, log_sha256:, negative_probes: []}
overhead: {unisolated_ms:, isolated_ms:, max_ratio_precommitted:}
review: {reviewer_id:, independent:, review_commit:, reviewed_at:, decision:}
contamination: {detected:}
```

## Empirical check November 7
A local reusable Python structural checker passed **14/14** unit tests. The conservative extraction from `evaluations/E011_A2_UID_PREFLIGHT_2026-11-03.md` returned **NOT_READY**, 37 rule-level field flags (overlapping). This establishes insufficiency of **inspected Markdown as a full release receipt**, not nonexistence of separate raw evidence. The program **never** emits an E011 PASS or releases E011-B, even for a well-formed synthetic object. Local script/tests/raw JSON/log are in downloadable user artifact; not claimed committed here.

## Admission process
1. R0 commits full attempt manifest before execution; independent reviewer audits the precommit.
2. Truly separated R1/R2/R3 model/workspaces execute the actual negative/positive probes and frozen transfer protocol.
3. Structural lint + third-party independent checks of real signed/artifact-hash/exposure/overhead receipts.
4. Reviewer issues separate PASS/FAIL/INVALID/INCONCLUSIVE adjudication. Only reviewed full A2 PASS can permit E011-B attempt precommit.
5. Do not change E004–E006 frozen material or promote this policy before separate human decision.

**Important:** linter cannot attest genuine context isolation, authenticity of signatures/logs, or completeness of OS/tool telemetry. It is an admission helper, never a security proof.
