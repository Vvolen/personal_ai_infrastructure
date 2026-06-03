# ChatGPT Task Setup: Biweekly AI Operating-System AutoResearch

Created: 2026-06-02
Timezone: America/Phoenix
Status: ready to paste into ChatGPT Tasks

## Important constraint

ChatGPT Tasks should be treated as a scheduled prompt runner and notification layer, not as the entire autonomous research system.

The Task's job is to trigger the loop, remind the user what state to load, and produce a bounded first-pass run or a run-request prompt. Deeper work can then happen in ChatGPT Agent Mode, Deep Research, Ponder, or a GitHub-backed workflow.

## Recommended task name

Biweekly AI OS AutoResearch Run

## Recommended schedule

Every other Tuesday at 9:00 AM America/Phoenix.

Suggested first run: 2026-06-16 at 9:00 AM America/Phoenix.

## Task instructions to paste

```text
Every other Tuesday at 9:00 AM America/Phoenix, run my AI Operating-System AutoResearch loop.

Your goal is to improve how I use AI every day. This is not an AI-news digest.

First, ask me to provide or open the current AutoResearch state if you cannot access it directly:
- autoresearch/STATE.md
- autoresearch/RUN_LEDGER.md
- the latest 1-3 files under autoresearch/runs/
- autoresearch/BIWEEKLY_AUTORESEARCH_GOVERNANCE_LOOP.md
- autoresearch/tasks/HIGH_LEVERAGE_CHATGPT_TASKS.md

Then run the governed loop:
1. Read previous state and latest run artifacts.
2. Compact the current doctrine.
3. Identify stale assumptions and open hypotheses.
4. Research what changed since the last run in AI workflow design, cognitive engineering, context engineering, memory engineering, agentic retrieval, evaluation loops, ChatGPT Tasks, Ponder-like workspaces, and AutoResearch-style systems.
5. Prioritize findings that can change behavior, not merely inform me.
6. Surface hidden unlocks.
7. Propose experiments for the next 14 days.
8. Update doctrine recommendations.
9. Produce a decision trace.
10. Prepare the next-run queue.

Use this evidence taxonomy:
- Fact: source-backed.
- Inference: reasoned from sources.
- Speculation: plausible but unvalidated.
- Recommendation: proposed action.

Output in this structure:

# AutoResearch Run YYYY-MM-DD

## Previous-State Readout
## What Changed Since Last Run
## Frontier Scan
## Hidden Unlocks
## Doctrine Updates
## New Artifacts
## Experiments for Next 14 Days
## Decision Trace
## Run Score
## Next-Run Queue

Score the run 1-5 on:
- novelty
- actionability
- evidence quality
- doctrine improvement
- compounding value
- integration readiness

Quality bar:
The run must produce at least one reusable artifact, one doctrine update, and one experiment. If it cannot access sources or prior state, it should produce a ready-to-run Agent Mode or Deep Research prompt instead of hallucinating.
```

## Why this task is designed this way

ChatGPT Tasks are valuable because they create cadence. Cadence is the bottleneck in compounding systems.

But the task itself should stay bounded. It should not try to do every possible research path indefinitely. The deeper research loop should happen through a follow-up Agent Mode or Deep Research run when needed.

## Operating model

1. Task fires.
2. It asks for current state or reads what is available.
3. It performs a bounded scan.
4. It creates the run artifact.
5. User or agent commits output to GitHub.
6. Every 3 runs, compact durable findings into STATE.md.

## Active task portfolio limit

Because ChatGPT Tasks has a limited number of active slots, keep only the highest-leverage recurring tasks active.

Recommended active set:

1. Biweekly AI OS AutoResearch Run.
2. Weekly Ponder Canvas Audit.
3. Monthly Prompt/Workflow Version-Control Audit.
4. Monthly Decision Trace Review.
5. Quarterly AI OS Governance Audit.

Avoid spending slots on generic reminders that normal calendar apps can handle.
