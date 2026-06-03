# High-Leverage ChatGPT Tasks Playbook

Created: 2026-06-02
Timezone: America/Phoenix
Status: bootstrap playbook

## Purpose

This file translates the recurring ChatGPT Tasks idea into a practical task portfolio.

The highest-leverage Tasks are not simple reminders. They are recurring reflection, review, research, synthesis, and compounding loops. The right task should make future work easier, not merely ping the user.

## Current capability assumptions

Based on public reporting, ChatGPT Tasks can schedule one-time or recurring prompts and send notifications. Reports from the initial beta described Tasks as available to paid users, managed through ChatGPT, with a limit around 10 active tasks. The feature is best treated as a scheduled prompt runner plus notification surface, not as a fully autonomous agent with unlimited tool autonomy.

Therefore the ideal design is:

- Use Tasks for trigger/cadence.
- Use GitHub/Ponder/Notion as memory and artifact stores.
- Use ChatGPT/Deep Research/Agent mode when deeper work is required.
- Keep each scheduled task scoped enough to succeed.
- Make tasks produce decision traces and next actions, not just summaries.

## Design principle

A great recurring AI task has five parts:

1. A stable cadence.
2. A clear state source.
3. A bounded research/action scope.
4. A compact output contract.
5. A compounding writeback target.

Bad task: "Tell me about AI news every two weeks."

Good task: "Every two weeks, read my AutoResearch state, identify doctrine gaps, research only what could change my operating system, score candidate upgrades, and produce experiments for the next 14 days."

## Task portfolio

### T001: Biweekly AutoResearch Doctrine Upgrade

Cadence: every 14 days
Priority: highest

Goal:
Upgrade the user's AI operating doctrine through governed research, compaction, and experiments.

Memory source:
- `autoresearch/STATE.md`
- latest 1-3 files under `autoresearch/runs/`
- `autoresearch/RUN_LEDGER.md`

Output:
- new run artifact
- doctrine updates
- next 14-day experiments
- hidden unlocks
- run score

Why it matters:
This is the central compounding loop.

### T002: Weekly AI Operating-System Review

Cadence: weekly
Priority: high

Goal:
Review how the user actually used AI during the week and identify where prompts, workflows, or tools failed to compound.

Prompt skeleton:

```text
Review my AI usage from the past week using any available notes, outputs, conversations, or artifacts I provide. Identify:
1. where AI saved significant time,
2. where it produced slop or friction,
3. which prompt/workflow should be promoted into a reusable asset,
4. which repeated task should become a scheduled task,
5. what I should stop doing.
Return one operating upgrade, one prompt upgrade, and one experiment for next week.
```

### T003: Daily/Every-Other-Day Focus Reset

Cadence: daily or weekdays
Priority: medium

Goal:
Prevent drift and restart momentum.

This is not a generic motivational reminder. It should ask what matters today, identify the highest leverage next action, and force a small win.

Prompt skeleton:

```text
Run a 3-minute focus reset. Ask me for my current working context if needed. Then return:
1. the one highest-leverage action for the next 45 minutes,
2. what to ignore,
3. a tiny first step,
4. a friction-removal suggestion,
5. one question that would improve my use of AI today.
```

### T004: Weekly Ponder Canvas Audit

Cadence: weekly
Priority: high if Ponder is actively used

Goal:
Turn Ponder into a compounding knowledge graph rather than a pile of canvases.

Prompt skeleton:

```text
Audit my active Ponder canvas/workspace. Identify orphaned notes, underlinked sources, stale assumptions, hidden relationships, contradictions, and output candidates. Produce:
1. one map to build,
2. one canvas to compact,
3. one source cluster to synthesize,
4. one hidden unlock,
5. one exportable artifact to create.
```

### T005: Monthly Prompt/Workflow Version-Control Audit

Cadence: monthly
Priority: high

Goal:
Treat prompts and workflows like code.

Prompt skeleton:

```text
Review my active prompt/workflow library. Identify prompts that should be versioned, prompts that are too long, prompts that lack output contracts, prompts that need evaluations, and workflows that should be promoted into reusable templates. Return diffs, not vague advice.
```

### T006: Biweekly Research Queue Curator

Cadence: every 14 days, offset from AutoResearch by 7 days
Priority: medium-high

Goal:
Maintain a living queue of questions worth researching.

Prompt skeleton:

```text
Review my current research questions and prior outputs. Rank the top 10 research questions by leverage, uncertainty, timing, and potential to change behavior. Retire stale questions. Add new frontier questions. Return the top 3 to investigate next and why.
```

### T007: Monthly Decision Trace Review

Cadence: monthly
Priority: high for compounding

Goal:
Inspect important decisions and capture the reasoning, assumptions, sources, and outcomes.

Prompt skeleton:

```text
Review recent major decisions and outputs. For each, capture a decision trace:
- decision
- input sources
- assumptions
- constraints
- tradeoffs
- expected outcome
- actual outcome if known
- what to remember next time
Then update the decision-trace doctrine.
```

### T008: Quarterly Governance Audit

Cadence: quarterly
Priority: high

Goal:
Audit the entire AI operating system.

Prompt skeleton:

```text
Audit my AI operating system: prompts, tasks, memory, retrieval, Ponder, GitHub, Notion, evaluation loops, and recurring workflows. Identify what has compounded, what has become ceremony, what should be automated, what should be deleted, and what should become doctrine. Produce a revised governance policy.
```

## Ranking

Best first three tasks:

1. T001 Biweekly AutoResearch Doctrine Upgrade
2. T004 Weekly Ponder Canvas Audit
3. T005 Monthly Prompt/Workflow Version-Control Audit

Most dangerous task if done poorly:

- Generic AI news digest. It creates the feeling of progress without operating-system change.

Best lightweight daily task:

- Focus Reset, but only if it asks for one concrete next action and one thing to ignore.

Best compounding task:

- Monthly Decision Trace Review because it captures the reasoning behind outputs, not just the outputs.

## Task quality checklist

Before creating any ChatGPT Task, ask:

- Does it have a state source?
- Does it have an output artifact?
- Does it have a scoring rubric?
- Does it update a doctrine, prompt, workflow, policy, or experiment?
- Does it avoid generic summaries?
- Is it bounded enough to succeed without going infinite?

If not, do not schedule it yet.
