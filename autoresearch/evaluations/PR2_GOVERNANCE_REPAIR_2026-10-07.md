# PR #2 governance consistency repair

Date: 2026-10-07, America/Phoenix
Status: proposed documentation repair on the existing draft PR; human review pending
Repository: `Vvolen/personal_ai_infrastructure`
PR: https://github.com/Vvolen/personal_ai_infrastructure/pull/2
Review branch: `autoresearch/run-006-2026-09-22`
Inspected branch head: `1e1452372fbb8c4035608ba828133802d998ee6e`
Inspected main: `f71c5b501df32c4655e5d96f9a2cb0f454b2e295`

## Observed defects

1. Run 007 named `autoresearch/policies/BELIEF_STATE_AND_MEMORY_VALIDITY_CONTRACT_V1.md`, absent from both inspected trees and their fetched path history.
2. State and ledger still ended at Run 006. Run 007, its A1 receipt and capability note were already on the PR branch.
3. The September 22 review comment left E011-B's commitment time unspecified, permitting threshold selection after observing calibration outputs.

The live PR was open, draft and unmerged. Run 005 remained the latest canonical run. Historical files on main still describe an older pre-merge snapshot; event state and ancestry establish that Runs 003–005 were accepted through PR #1. This repair targets PR #2 only.

## Repair

- Indexed Run 007 as completed research on the review branch, still proposed; recorded Run 008 as the next planned run on October 20 without advancing accepted-run counts.
- Materialized the missing policy on October 7 with belief schema, candidate validation/commit, read-time validity, progress/recovery, negative knowledge, multi-agent merge rules and artifact-bound evaluation. It remains a proposal awaiting E009-A and human review.
- Added the current board, `autoresearch/experiments/2026-10-06_to_2026-10-20.md`, and linked it from state, ledger, and the dated Run 007 clarification.
- Corrected the original E011-B board and Run 006 policy to require `autoresearch/evaluations/E011_B_PRECOMMITMENT_V1.md`. Exact splits, numeric thresholds, evaluator versions, scoring and pass/fail rules must be frozen before any calibration or evaluation outputs. Same-attempt calibration tuning is prohibited; invalid exposure or changed rules require a new attempt.
- Preserved the A1 receipt and original run body. The dated clarification reconciles the two summarized attacks with the receipt's third, post-freeze attack. A1 is a recorded policy-only PASS, not a new runtime verification.
- Separated reviewed A2/B permission for recovery attempts from full E011 completion. E011 retains the original requirement for two valid E004–E006 results and its overhead/receipt gates; its missed September 22 target is not backdated or declared met.

## Verification

- Baseline reference/invariant audit at the inspected PR head exited nonzero: the belief-state policy was missing, Run 007 was not indexed/current, and the next-run/subtest state was stale.
- Repaired-tree audit passed across 35 AutoResearch Markdown documents and 126 local document-reference occurrences, with zero missing references and zero failed state invariants. The audit resolves repository-relative, document-relative and unique-basename references, excluding illustrative fenced templates; it does not verify external URLs or scientific claims.
- State checks preserved Run 005 as latest canonical, Runs 006–007 as review-branch history, Run 008 as next planned run, D-AR-001–019 without new identifiers, zero E004–E010 substantive results, and A1/A2/B's distinct statuses.
- SHA-256 checks matched all four precommit hashes: outer governance and E004/E005/E006 datasets. The active-doctrine section is byte-for-byte unchanged from the inspected PR head. Historical A1 and other result receipts are unchanged.
- Staged `git diff --cached --check` passed with exit 0; any whitespace diagnostic or nonzero exit would fail this check. These are document-consistency checks, not new experiment results.

## Review and limits

An independent, read-only Gemini 3.8 Flash review of the revised state, ledger, current board and two new contracts found no blockers. The lead checked its suggestions against the documents. The existing “completed on review branch” label was retained with explicit proposed-status text; exact metric functions remain mandatory attempt-specific fields, so execution stays blocked until they are supplied. Prose fields for negative knowledge are required contract fields, not an implemented runtime schema. Queue formatting does not change its order. The lead also tightened numeric domain checks to prevent a zero-coverage/all-abstention policy from passing.

This review assesses the consistency of a proposed documentation repair. It is not approval of doctrine or experiment results. No E011-A2/B execution, new E004–E006 result, E009-A result, external paper/product re-verification, or policy promotion was performed. The September review thread should remain open for the reviewer to assess the response.

## Remaining state and exact next action

- Latest canonical run: 005. Latest proposed run: 007. Runs 006–007 remain under PR #2 review.
- E003 remains PASS; E004–E006 blocked; E007 reframed; E008 parked; E009/E010 proposed/unexecuted.
- E011 is PARTIAL: A1 has a policy-only receipt; A2 and B are unexecuted. No attempt-specific E011-B manifest or numeric threshold selection is claimed.
- Human reviewer: review this repair and the E011-B thread on PR #2. After the relevant review, execute A2, then populate and independently check a complete B precommitment before generating any B outputs. Doctrine adoption requires its separate recorded human decision.

Authorized delivery is limited to updating the existing draft PR and its review response. No merge or promotion. If the repair is rejected, revert its commit on the review branch; preserve prior run and evaluation history. Main and frozen evaluation assets are unchanged by this repair.
