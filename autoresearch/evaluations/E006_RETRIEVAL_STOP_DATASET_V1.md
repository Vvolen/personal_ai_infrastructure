# E006 Retrieval-Stop Dataset v1

Status: frozen evaluation artifact
Frozen: 2026-08-14
Experiment: E006 — Evidence-sufficiency retrieval stop rule
Split: 6 development / 4 held-out

## Evaluation contract

Run Lane A with the frozen fixed-source budget and Lane B with the candidate sufficiency gate plus the same hard maximum. Hold model, tools, evaluator, environment, and as-of date constant. The frozen source cutoff is 2026-08-14 unless a case states an earlier date. Record every query, source opened, tokens retrieved, stop decision, unresolved gap, supported-claim rate, and missed contradiction. Only development cases may tune the threshold or weights.

For every case, the final artifact must separate source fact, practitioner signal, inference, recommendation, and unresolved evidence. A low-cost answer fails if it misses a required contradiction or materially overstates a source.

## Development questions

### E006-D01 — Single-authority stop

Question: What file-access limitation in OpenAI Scheduled Tasks matters to a recurring project-backed research task as of 2026-08-11, and what is the narrow architectural implication?

Evidence target: one current authoritative OpenAI source may be sufficient; do not add secondary sources merely to hit a quota. The implication must remain labeled as inference.

### E006-D02 — API contract requires escalation

Question: Does the documented Workspace Agent API-trigger response provide enough information to retrieve a durable run result as of 2026-08-11?

Evidence target: inspect official trigger and result/observability documentation. Stop only after both the request contract and response/retrieval boundary are established or the missing documentation is explicitly recorded.

### E006-D03 — Repository identity and mechanism

Question: Which repository is Andrej Karpathy's official AutoResearch project, and what files establish its editable surface and objective loop?

Evidence target: verify owner/repository identity, README claims, and relevant executable/configuration files. Popularity or name match alone is insufficient.

### E006-D04 — Framework capability boundary

Question: Does LlamaIndex's ingestion pipeline by itself provide governed canonical truth and human approval for durable knowledge promotion?

Evidence target: establish shipped ingestion/document-management capabilities from official sources, then label the governance conclusion as an inference from what is and is not documented.

### E006-D05 — Optimizer evidence boundary

Question: What does a better DSPy development metric establish, and what additional evidence is needed before promoting a research-harness change?

Evidence target: official DSPy optimizer/evaluation material plus primary evaluation principles where needed. Look explicitly for overfitting or held-out limitations; do not infer production reliability.

### E006-D06 — Review-thread state

Question: Which GitHub API surface preserves pull-request review-thread resolution state and file anchors, and which separate mutations can change conversation state?

Evidence target: official GitHub GraphQL/REST documentation. Distinguish read data from reply, resolve, push, and merge actions.

## Held-out questions

### E006-H01 — Upstream/fork delta

Question: Is `Vvolen/personal_ai_infrastructure` a current upstream project or a stale fork/adaptation, and what exact repository evidence supports the answer?

Evidence target: GitHub metadata, remotes/fork relationship where exposed, commit dates, and file/history comparison. Stop only when identity and freshness are both supported; record inaccessible evidence.

### E006-H02 — Practical research-compounding claim

Question: What evidence would demonstrate that a domain research system is compounding understanding rather than accumulating assisted outputs?

Evidence target: primary learning/evaluation research and official evaluation tooling as appropriate. Require delayed or held-out transfer, provenance, calibration or error evidence, and a fresh baseline; resist endless framework collection.

### E006-H03 — Foundation Layer versus LlamaIndex

Question: Which capabilities in the user's Foundation Layer repository, if any, remain differentiated from current LlamaIndex primitives?

Evidence target: inspect both repositories and runnable evidence. A valid stop may be “not testable” if the target repository cannot be identified or executed; never fill gaps by analogy.

### E006-H04 — Conflicting practitioner method

Question: A practitioner claims autonomous research improves simply by retaining every prior note, while primary evaluation literature warns about contamination and unmeasured transfer. What policy should govern retention and promotion?

Evidence target: recover the actual practitioner claim and primary evaluation evidence, represent the disagreement faithfully, and propose a bounded local test. Do not resolve the conflict by source-count voting.
