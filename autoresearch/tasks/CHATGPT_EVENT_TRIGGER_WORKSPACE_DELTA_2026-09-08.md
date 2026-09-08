# ChatGPT Event-Trigger & Workspace Capability Delta — 2026-09-08

Status: current capability note  
Linked run: `autoresearch/runs/2026-09-08_run_005.md`

## Executive delta

The architectural boundary of Scheduled Tasks has changed materially since the August notes:

> Scheduled Tasks are no longer only clock-based recurring/monitoring triggers. Eligible paid plans can now create **event-triggered tasks** from supported Gmail, Slack, and GitHub events, and those tasks run in ChatGPT Work.

This expands the trigger plane without making Tasks canonical state.

## Verified current capabilities

### Event-triggered tasks

OpenAI currently documents event-triggered tasks for eligible Plus, Pro, Business, Enterprise, Edu, and Healthcare users.

Supported event families include:
- new Gmail messages;
- Slack channel messages;
- GitHub pull-request activity.

Event-triggered tasks execute through Work and can run when qualifying events arrive rather than waiting for a fixed clock schedule.

Actions that require user approval pause at the approval boundary.

### Frequency / quota distinction

Recurring scheduled tasks remain limited to hourly-or-slower cadence.

Event-triggered tasks have a different event budget and may fire substantially more frequently than hourly, subject to documented account/task limits.

### Project-file limitation survives

A Scheduled Task created in a Project with uploaded files still cannot rely on those Project-uploaded files as its durable state source.

Therefore the existing canonical-state rule survives:

```text
Trigger
  scheduled / monitoring / event-driven
            ↓
Canonical state preflight
  GitHub / explicit ledger / connected source
            ↓
Work / Hermes / Codex / governed runtime
            ↓
Artifact + evaluation + reviewable writeback
```

## Proposed capability amendment to D-AR-006

Current doctrine title remains correct:

**D-AR-006 — Tasks Are Triggers, Not Canonical State**

Amend its explanatory text to:

> Scheduled Tasks may initiate one-off, recurring, monitoring, or supported event-triggered Work flows. Trigger history is operational context, not authoritative doctrine/state. Every governed run must re-read canonical external state and write durable results back through the governance layer.

This is a capability update, not a change to the authority boundary.

## AutoResearch unlock: PR-aware wakeups

A GitHub PR event-triggered task can potentially shorten the 14-day dead zone around the AutoResearch review loop.

Candidate pattern:

```text
PR #1 review/comment/change event
        ↓
GitHub event-triggered ChatGPT Task
        ↓
Work reads PR metadata + canonical/review state
        ↓
classify event:
  review blocker / accepted change / irrelevant noise
        ↓
produce compact review-state update
        ↓
human approval where required
```

This should **not** merge the PR automatically and should not promote doctrine from a review comment alone.

## WebMCP / Sites delta

OpenAI's current desktop/browser release notes describe Work/Codex browser support for site-provided tools through WebMCP. Sites can also be shared with named external people as view/use surfaces.

Implication:
A future cognitive cockpit does not have to be a passive dashboard. A Ponder-like or Site-like surface could expose typed governed actions if its runtime supports a compatible tool contract.

This is an interface opportunity, not evidence that Ponder currently exposes WebMCP or a public orchestration API.

## GPT-6 Astra delta

OpenAI announced GPT-6 Astra on 2026-09-03 with stronger multi-step work, research, coding, computer use, and artifact creation. API documentation also describes mid-turn steering in supported realtime/WebSocket interactions.

Policy implication:
Model capability is improving, but AutoResearch evaluation must continue to pin the model snapshot in every evaluation tuple. A harness result under one model version cannot be treated as model-independent.

## Ponder status

Ponder's public beta continues to center on collaborative agents, intelligent tools, action plans, direct editing, and execution tracking.

No verified public developer/runtime API surfaced in this scan.

Therefore:
- Ponder remains a cognitive-cockpit candidate;
- GitHub remains canonical governance state;
- E007 should test both review quality and whether the interface can expose governed typed actions.

## Primary sources

- OpenAI, Scheduled Tasks in ChatGPT: https://help.openai.com/en/articles/10291617-scheduled-tasks-in-chatgpt
- OpenAI, ChatGPT release notes: https://help.openai.com/en/articles/6825453-chatgpt-release-notes
- OpenAI, product release notes: https://openai.com/products/release-notes/
- Ponder: https://ponder.do/
