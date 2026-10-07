# E011-B precommitment protocol v1

Created: 2026-10-07
Status: proposed protocol; execution blocked until an attempt-specific record is complete
Review finding: https://github.com/Vvolen/personal_ai_infrastructure/pull/2#discussion_r4074169471
Current board: `autoresearch/experiments/2026-10-06_to_2026-10-20.md`

## Commitment boundary

Before running, generating, or inspecting **any calibration or evaluation outputs**, judge scores, grounded outcomes, or disagreements for an E011-B attempt, R0 must commit a complete precommitment record and have its completeness/exposure receipt checked by an independent reviewer. The record must fix the exact calibration/evaluation split, numeric abstention thresholds, evaluator configuration, and pass/fail calculation. The commit, content hashes, and access logs establish ordering; a retrospective timestamp does not.

No populated attempt record, selected numeric thresholds, split assets, or execution receipt exists in this repair. This protocol alone cannot authorize a run or claim a precommitment has happened. Unknown prior exposure blocks the attempt. B also waits for a reviewed E011-A2 isolation pass.

## Required attempt record

Every field below is mandatory before execution. A blank, placeholder, missing asset/hash, or non-numeric threshold means BLOCKED.

| Field | Required fixed content |
|---|---|
| Identity and ordering | Attempt ID/version, task family, owner, independent reviewer, commitment commit/time/hash, first-execution time to be appended to the result, prior-exposure attestation and access-log hashes |
| Dataset and split | Versioned task IDs, related-task/group IDs, assignment rule/seed, exact counts, disjoint calibration/evaluation manifests and SHA-256 hashes; at least 20 tasks total, at least 10 in each split |
| Assets | Immutable stimuli and evaluator keys, hashes and protected locations; selection/exclusion rules fixed without candidate/judge output inspection |
| Candidate and comparators | Exact candidate and judge-only baseline versions, model snapshot, prompts, tool/environment hashes, seeds/repetitions, aggregation and retry policy |
| Grounded and artifact checks | Versioned verifier, objective completion bit definition, artifact rubric and numeric cutoff, scoring implementation/hash |
| Judge rule | Score/confidence scale, eligibility cutoff, **numeric abstention threshold**, exact inclusive/exclusive comparisons, missing/non-finite output handling, numeric valid range |
| Calibration gate | Numeric maximum disagreement/error and minimum non-abstained coverage; exact numerator/denominator and close-pair definition/pair IDs, tie and empty-set rules |
| Evaluation gate | Numeric maximum false-negative rate and minimum coverage; close-pair agreement limit; fixed metric implementation; the pass conjunction below |
| Isolation | R0/R1/R2/R3 identities and path permissions, A2 receipt, candidate/output freezes, transfer rules, exposure log format |

Thresholds must be finite numbers on declared scales, never phrases such as “acceptable disagreement.” Require `0 < minimum_coverage <= 1`, `0 <= maximum_false_negative_rate < 1`, and disagreement limits within `[0, 1]`; reject out-of-range settings before execution. The frozen numeric abstention comparison must define behavior exactly at the threshold. Asset and scoring hashes are SHA-256 over the exact bytes. Avoid overlapping tasks, paraphrases, shared source cases, or other related groups across splits. Counts and assignments cannot change after outputs are available. Evaluator keys stay inaccessible to the developer and runner under the isolation contract.

## Execution order

1. Independently verify that the precommitment is complete and predates all attempt outputs; verify hashes and clean exposure. Otherwise STOP with BLOCKED or INVALID.
2. Run calibration under the frozen policy. Calibration assesses whether that policy is usable; it does **not** choose thresholds or fit the judge within this attempt. Apply its precommitted gate. If it fails, record FAIL and do not release the evaluation split for that attempt.
3. Run the same frozen candidate, judge-only comparator, and anchored gate on the independent evaluation split. The developer never receives evaluation stimuli/keys; R2 receives stimuli only after candidate freeze, R3 keys only after outputs freeze.
4. Calculate final pass/fail from the evaluation split only. Report calibration diagnostics separately; never pool them into the evaluation denominator.
5. Publish frozen raw outputs, per-case decisions, exposure/transfer receipts and all metrics, including failures, abstentions, exclusions fixed in advance, and missing outputs. Bind them to the committed plan and exact candidate.

Changing a threshold, split, rubric, judge, model, candidate, verifier, or scoring rule after seeing outputs invalidates a release claim for that attempt. Preserve it as diagnostic evidence. A revised attempt needs a new precommitment and fresh unexposed calibration/evaluation assets and contexts. Never relabel inspected evaluation cases as untouched. Learned policy changes can be proposed for the new attempt only.

## Decision calculation

For each evaluation task, derive `G` from the frozen grounded verifier, `A` from the frozen artifact gate, `J` from the frozen judge eligibility cutoff, and `S` from the frozen numeric abstention rule. These are simulated eligibility decisions, not actual promotions:

```text
judge_only_eligible = J and not S
anchored_eligible = (G == PASS) and (A == PASS) and J and not S
```

Grounded FAIL or UNKNOWN can never yield anchored eligibility. Missing/error outputs stay in the assigned-case record and cannot be silently dropped or rerun until favorable. Treat them as abstentions/ineligible; an unknown grounded outcome also makes the release result INCONCLUSIVE because its class denominator cannot be established.

Report raw counts and these evaluation-only rates for each gate:

- false-promotion rate = eligible grounded failures / all grounded failures;
- false-negative rate = ineligible grounded successes / all grounded successes;
- coverage = eligible cases / all assigned evaluation cases;
- abstention rate = abstained cases / all assigned evaluation cases.

Also report the precommitted ranking/construct/close-pair disagreement metrics, with exact denominators and ties. The task/pair manifest must support those metrics. Empty or undefined required denominators, no grounded failures or successes, or zero false promotions by the judge-only comparator make the claimed improvement INCONCLUSIVE, never PASS. Report task-family and sample-size limits; a small synthetic sample is not a general performance guarantee.

PASS requires all of:

- reviewed A2 pass, valid precommitment, unchanged hashes/configuration, and clean isolation/exposure;
- calibration gate passed without tuning;
- complete, evaluable evaluation-case records;
- zero anchored eligibility decisions on grounded FAIL or UNKNOWN;
- strictly lower anchored false-promotion rate than judge-only on the same evaluation cases;
- anchored false-negative rate at or below its frozen maximum, and coverage at or above its frozen minimum, so abstaining on everything cannot pass;
- required disagreement metrics within their frozen bounds.

A valid, evaluable attempt violating a numerical gate is FAIL. Late commitment, contamination, or changed assets/rules is INVALID. Missing setup is BLOCKED. Undefined evidence of improvement is INCONCLUSIVE. None permits downstream release. Retain the hypothesis as unproven unless the entire conjunction passes.

## Receipt and release boundary

The result records plan commit/hash, exact split and scoring hashes, numeric thresholds, candidate/output hashes, model/verifier versions, environment, execution/release/freeze times, role exposure, calibration metrics, evaluation metrics and denominators, status/reasons, and independent review decision.

Reviewed A2/B passes permit isolated E006, then E005/E004 attempts. They do not count as those experiments' results and do not complete E011, which retains the two-result and overhead/receipt gates from `autoresearch/experiments/2026-09-08_to_2026-09-22.md`. Doctrine promotion remains a separate human decision. A documentation repair never substitutes for these execution receipts.
