# E004 Frontier-Scan Dataset v1

Status: frozen evaluation artifact
Frozen: 2026-08-14
Experiment: E004 — Bounded task-specific harness evolution
Split: 8 development / 4 held-out

## Evaluation contract

Each case is run once with the baseline harness and once with the candidate harness under the same model snapshot, tool manifest, environment, time limit, and as-of date. The frozen source cutoff is 2026-08-14 unless a case states an earlier date. Only the development cases may influence candidate edits. Held-out cases are released to the execution harness only after candidate versions are frozen.

Score every case on unsupported-claim rate, primary-source coverage, redundant source reads, tool calls, retrieved tokens, accepted-artifact status, source-to-claim traceability, and critical errors. A critical error is a fabricated source, a material claim contradicted by its cited source, an unstated breach of the as-of date, or a recommendation represented as an established fact.

## Development cases

### E004-D01 — Scheduled-task capability delta

Prompt: As of 2026-08-11, verify the documented capabilities and limitations of OpenAI Scheduled Tasks that matter to a file-backed recurring research workflow. Separate facts from architectural implications and identify what cannot be concluded from the documentation.

Acceptance anchors: prefer official OpenAI documentation; cover file/project access, supported interaction modes, cadence or activity constraints, and durable-state implications; retain uncertainty where documentation is silent.

### E004-D02 — Workspace-agent orchestration boundary

Prompt: As of 2026-08-11, determine whether OpenAI Workspace Agents can serve as a complete durable orchestration protocol for AutoResearch. Inspect documented schedules, API triggers, tools, files, response retrieval, and run observability. Return a direct adoption verdict with evidence.

Acceptance anchors: official OpenAI documentation; distinguish available, eligible, configured, and operational; do not infer missing response or state contracts.

### E004-D03 — GitHub review-thread control surface

Prompt: Design the smallest GitHub-backed review workflow that preserves inline review-thread identity, resolution state, exact file anchors, and human authorization before merge. Verify the relevant API capabilities and state which operations remain separate write actions.

Acceptance anchors: official GitHub REST/GraphQL documentation; distinguish reading, replying, resolving, pushing, and merging; preserve least authority.

### E004-D04 — LlamaIndex ingestion boundary

Prompt: Using current official LlamaIndex documentation and source material, explain what its ingestion pipeline, indexes, retrievers, and document-management features do. Identify which parts are reusable infrastructure and which parts do not by themselves establish canonical truth, provenance governance, or promotion authority.

Acceptance anchors: official LlamaIndex documentation or repository; separate shipped capability from system-design inference; avoid product-comparison hype.

### E004-D05 — DSPy optimization prerequisites

Prompt: Verify how DSPy optimizers use metrics, training/development examples, and evaluation. Explain what must be frozen before using an optimizer to improve an agent research harness and what evidence would still be missing after a better development score.

Acceptance anchors: official DSPy documentation or repository; cover metric quality, dataset splits, held-out testing, and overfitting risk; mark recommendations as recommendations.

### E004-D06 — Repository-to-doctrine provenance

Prompt: Given a public AI repository with a persuasive README, define and justify an evidence chain for deciding whether one mechanism should enter a personal operating doctrine. Include repository state, executable evidence, evaluation evidence, applicability, a falsifiable local test, and a promotion receipt.

Acceptance anchors: use primary repository/docs evidence for examples; distinguish popularity and architectural coherence from operational proof; produce a reusable decision record.

### E004-D07 — Long-horizon trajectory evaluation

Prompt: Investigate primary research and official tooling relevant to evaluating long-horizon agent trajectories. Compare final-artifact scoring with process or component attribution, then propose a bounded local evaluation that can detect a correct answer produced through an invalid process.

Acceptance anchors: primary papers and official tool documentation; preserve paper limitations; separate reported findings from local proposal.

### E004-D08 — Governed memory lifecycle

Prompt: Research how an agent memory system should handle ingest, scope, retrieval, correction, consolidation, forgetting, and provenance. Produce a boundary-first architecture in which human-correctable canonical files outrank derived indexes or generated summaries.

Acceptance anchors: primary papers, specifications, or official repositories; identify unsupported design choices; include correction and rollback paths.

## Held-out cases

### E004-H01 — AutoResearch mechanism audit

Prompt: Identify the current official Andrej Karpathy AutoResearch repository and explain its actual optimization loop, benchmark boundary, editable surface, and transfer limits for knowledge-work research. Distinguish repository facts from proposed adaptation.

Acceptance anchors: repository code, README, and history; verify identity rather than relying on name similarity; do not equate benchmark improvement with expertise compounding.

### E004-H02 — Personal-AI-infrastructure upstream delta

Prompt: Identify the current original upstream for this personal AI infrastructure repository, compare the fork's relationship and staleness to upstream, and extract only mechanisms that are present in the current upstream. State what should be synced, studied, or kept local.

Acceptance anchors: GitHub repository metadata, commit history, and source files; distinguish verified delta from recommendation; do not overwrite local governance decisions with upstream prose.

### E004-H03 — Claim-level research compounding

Prompt: Design a falsifiable two-cycle protocol for determining whether research on a new domain genuinely compounds. It must compare a fresh model, an accumulated system, and human-plus-system performance while preventing held-out contamination and preserving source-to-claim provenance.

Acceptance anchors: primary learning/evaluation research or official evaluation tooling; define frozen artifacts, exposure logs, transfer tests, critical errors, and promotion/rollback decisions.

### E004-H04 — Foundation-layer differentiation test

Prompt: Audit a repository described as a data-refinement foundation layer and determine whether it has distinctive value relative to current ingestion, indexing, and retrieval frameworks. Produce keep, extract, archive, or revive criteria based on inspectable code, tests, provenance, and an executable vertical slice.

Acceptance anchors: inspect the target repository and official comparison-framework sources; do not infer equivalence from naming; separate reusable idea, working implementation, and current maintenance state.
