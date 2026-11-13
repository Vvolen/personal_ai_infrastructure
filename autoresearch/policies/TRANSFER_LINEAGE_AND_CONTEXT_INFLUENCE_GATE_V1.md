# Transfer-Lineage and Context-Influence Gate v1
Created: 2026-11-04
Status: **PROPOSED — NOT ACTIVE**
Run: `autoresearch/runs/2026-11-04_run_009S.md`
Experiment: E011-A2-L0 (synthetic policy preflight; not full isolation)

## Problem
Run 009's context-admission contract labels source content. It does not on its own prove how untrusted influence propagates through decoding, summarization, memory retrieval, subagent handoffs, and apparently trusted final artifacts. Signature authenticity is not directive authority.

## Proposed D-AR-007 amendment (not promoted)
At every cross-agent/tool-output transformation, preserve broker-owned source ancestry, source hashes, authority class, context-exposure lineage, receiver role and scope. An agent may not relabel its own untrusted inputs or erase prior context exposure. Sensitive action sinks validate both artifact dependencies and context influence. A signature on a derived object does not erase untrusted ancestors. An authorized independent promotion must be explicitly scoped, reviewable and revocable.

## Proposed D-AR-019 clarification (not promoted)
Passing deterministic lineage checks is **not** independent evaluation-context isolation. Actual R1/R2/R3 separate workspaces, model contexts, frozen transfer receipts and independent review are still required.

## Minimal broker-owned receipt
```yaml
transfer_receipt:
  transfer_id:
  source_id:
  source_sha256:
  derived_id:
  derived_sha256:
  parent_transfer_ids: []
  authority_class:
  receiver_role:
  receiver_context_id:
  exposure_record_id:
  transformation:
  time:
  issuer:
  integrity_tag:
  allowed_sinks: []
  approval_ref: null
  disposition: admitted_as_data
```

## Candidate algorithm
Fetch and hash original material; record transformations as parent-child edges; propagate inherited untrusted influence and model-context exposures; verify every relevant ancestor and any independent scoped approval at a consequential action sink; fail closed if lineage, authority or mediation coverage is unknown. Evaluate unauthorized acceptance **and** legitimate task false-rejection.

## Local E011-A2-L0 synthetic preflight
On 2026-11-04 a toy in-memory HMAC/broker unit test passed ten deterministic checks: clean trusted allowed; decoded untrusted parent denied; forged label denied; valid derived label with untrusted ancestry denied; untrusted context denies action using a clean artifact; legitimate read-only processing allowed; worker self-promotion denied; independent narrow override; unknown sink denied; changed parent denied.

**PASS_LIMITED** only. Not an actual MCP runtime, not independent LLM contexts/workspaces, no security review, no overhead benchmark, no verified end-to-end mediator. It does **not** release E011-B or E004–E006. Local runnable `e011_a2_lineage_preflight.py` and `E011_A2_L0_TEST_RECEIPT_2026-11-04.json` are available in the run's local deliverable bundle, not claimed as committed here.

## Adoption gates
Independent security audit; true separate workspaces/model contexts; complete transfer/exposure receipt coverage; precommitted adversarial and legitimate cases; operating-cost measurement; reviewed false-accept and false-denial rates; explicit human promotion decision. Do not silently modify frozen E004–E006 evaluation sets.

## Sources
- https://arxiv.org/abs/2610.31974 (submitted 2026-10-22; results scoped to fully mediated MCP contexts)
- https://arxiv.org/abs/2610.38521 (submitted 2026-10-28)
- `autoresearch/policies/UNTRUSTED_CONTEXT_ADMISSION_CONTRACT_V1.md` (Run 009)
