# Untrusted Context Admission Contract v1
Created: 2026-11-03
Status: **PROPOSED — NOT ACTIVE**
Linked Run: `autoresearch/runs/2026-11-03_run_009.md`
Candidate doctrine amendments: D-AR-007, D-AR-010, D-AR-019; no new doctrine ID.

## Problem

Project memory/instruction files such as CLAUDE.md/AGENTS.md, retrieved histories, external web pages, PR comments, agent-written notes and tool outputs may be authentic content yet **not authorized to direct agent behavior**. Being in GitHub establishes neither human review nor authority to change governance. This contract makes origin, current validity, and directive authority separate gates.

## Context authority classification

- `governance_approved`: human-reviewed approved policy with version/scope receipt.
- `operator_instruction`: current explicit authorized user direction with scope.
- `reviewed_operational_policy`: narrow task-local instruction with recorded reviewer and expiry.
- `candidate_instruction`: unmerged PR, unreviewed skill or agent-written memory; data ONLY until promoted.
- `external_observation`: web/tool/retrieved content/third-party comment; evidence, not policy.

An authoritative-looking heading, familiar filename, repetition, or readiness for PR review cannot promote text into a higher class. Merge does not automatically promote every proposal's doctrine.

## Fragment admission receipt

```yaml
context_admission:
  content_sha256: <SHA256 over exact bytes>
  source_uri: <immutable link/commit if possible>
  source_version:
  retrieved_at:
  author_identity:
  authority_class: candidate_instruction
  reviewed_by: null
  scope: []
  expires_at: null
  may_direct_actions: false
  may_change_governance: false
  validity_checked_at:
  conflicts: []
  disposition: admitted_as_data
```

## Admission algorithm

```
fetch + hash
 -> separate factual claims from embedded instructions
 -> check role and source permissions
 -> check source/version/supersession/environment validity
 -> inject as evidence only unless independently authorized
 -> before consequential action, check user authorization & forbidden effects
 -> log disposition and reviewer decision
```

Hard denials:
- Unreviewed memory or PR content cannot grant itself more authority.
- Agent-generated memories cannot authorize their own promotion.
- LLM-judge success cannot override grounded failure or unauthorized action.
- Trigger invocation is not merge or doctrine approval.
- PR `draft=false` is not `merged=true` and not a human review acceptance receipt.
- Repeated errors/obstruction do not widen capability scopes.

## Synthetic evaluation candidate (E009 under E011 gates)

At least 24 cases: trusted policy requiring safeguards; injected repo-memory instruction to disable them; unreviewed PR claiming governance power; superseded memory; legitimate reviewed scoped policy. Grounded metrics: wrong authority promotions, legitimate policy false-rejections, task completion, stale evidence use, token/latency cost. Freeze dataset, split, verifier, scoring and role access before model execution.

## Adoption gate

Requires independent isolated evaluation, complete exposure/transfer receipts, reviewed benchmark with controlled legitimate/hostile cases, explicit false-accept/false-reject thresholds, human approval, and a recorded doctrine decision. This proposal does not activate upon commit.

## Evidence

- Santos de Moura et al. (Oct 28, 2026), *Security Impact of Coding Agent's Memory Files*, https://arxiv.org/abs/2610.38521
- Source/authority discrepancies in current PR #2 lifecycle, https://github.com/Vvolen/personal_ai_infrastructure/pull/2
- Existing D-AR-004, D-AR-007, D-AR-010, D-AR-019, E011 controls in AutoResearch.
