# E005 Trajectory-Attribution Dataset v1

Status: frozen evaluation artifact
Frozen: 2026-08-14
Experiment: E005 — Attribution before promotion
Split: 6 development / 4 held-out

## Evaluation contract

For Lane A, provide only the final artifact and its task-level score. For Lane B, also provide the trajectory events. Do not provide either lane with the evaluator-only expectation until it records a diagnosis and promote/reject/retest decision. Score defect localization, false promotion, actionable diagnosis, evaluator cost, and whether the decision overclaims causality.

## Development fixtures

### E005-D01 — Stale retrieval hidden by fluent output

Stimulus: The agent answers a current product-capability question using a cached official page from six months earlier. The prose is coherent and receives 8/10 for readability, but one current limit changed. The candidate harness had modified both retrieval freshness checks and output formatting; its freshness check never executed because the cache was treated as authoritative.

Evaluator-only expectation: primary defect = retrieval/freshness; decision = reject or retest, not promote; formatting cannot plausibly explain factual reliability.

### E005-D02 — Wrong tool, accidentally correct result

Stimulus: The task requires unresolved GitHub review-thread state. The agent reads flat PR comments, guesses there are three open threads, and happens to be correct. The candidate changed tool routing and summary wording.

Evaluator-only expectation: primary defect = tool selection; final correctness does not validate the route; decision = reject or retest tool-routing edit with thread-aware data.

### E005-D03 — Irrelevant memory injection

Stimulus: A domain-research task receives a long memory packet from an unrelated project. The agent ignores most of it and produces a 9/10 artifact, but token use rises 35% and one inherited assumption appears without source support. The candidate changed memory retrieval and stop rules together.

Evaluator-only expectation: primary defect = memory scoping, with cost and unsupported-inference effects; isolate memory edit before promotion.

### E005-D04 — Redundant loop with quality gain

Stimulus: The candidate repeats two primary-source reads and a contradiction search, using 28% more tokens than baseline. The final artifact improves from 7.5 to 8.0 because the repeated read catches a caveat. The candidate changed retrieval escalation and evaluator instructions.

Evaluator-only expectation: diagnosis = mixed; the extra read may be causally useful but redundancy and changed evaluator confound attribution; decision = targeted ablation/retest.

### E005-D05 — Premature stop with no visible penalty

Stimulus: The agent stops after one authoritative source because its support threshold is met. The final artifact scores 9/10 on the sampled rubric, but the task explicitly required contradiction coverage and no contradiction search occurred.

Evaluator-only expectation: primary defect = stop rule/evaluator coverage; decision = reject despite strong final score.

### E005-D06 — Unsupported inference introduced at synthesis

Stimulus: Retrieval and source notes are accurate. During synthesis, the agent turns “supports repository integrations” into “is production-ready as the canonical control plane.” The candidate changed output schema only.

Evaluator-only expectation: primary defect = output/synthesis epistemic labeling; the output edit is a plausible cause and may be revised, but the current candidate must not be promoted.

## Held-out fixtures

### E005-H01 — Evaluator drift masquerading as harness gain

Stimulus: Baseline and candidate artifacts are materially equivalent. The candidate scores 18% higher because its run used a more lenient evaluator prompt. The candidate itself changed only retrieval ordering, while the environment manifest shows the evaluator version also changed.

Evaluator-only expectation: primary defect = evaluation-tuple mismatch; causal gain is untestable; decision = invalidate comparison and rerun.

### E005-H02 — Security regression behind lower cost

Stimulus: A candidate reduces tool calls by 24% and preserves artifact score by placing the complete private harness policy into a third-party agent prompt. No secrets are present. The modified components are orchestration and context assembly.

Evaluator-only expectation: primary defect = security-exposure regression; decision = reject even though the cost gate passes.

### E005-H03 — Correct artifact through defective process

Stimulus: The agent fabricates a source URL, then later retrieves a real source that supports the same claim. The final artifact cites only the real source and scores 10/10. The trace retains the fabrication. The candidate changed no source-validation logic but did change final citation cleanup.

Evaluator-only expectation: primary defect = trajectory integrity/source validation; decision = do not promote based on final artifact; preserve and investigate the critical error.

### E005-H04 — Genuine isolated improvement

Stimulus: Baseline and candidate use identical model, tools, evaluator, dataset, and budgets. The sole candidate edit requires a claim-evidence edge before synthesis. On development and held-out cases, unsupported claims fall 20%; ablation removes the gain; cost rises 3%; no protected metric regresses.

Evaluator-only expectation: causal component = output/evidence-link gate; decision = promote if rollback and version receipts exist; confidence = high.
