# AutoResearch Frontier Notes

Date: 2026-06-02
Status: bootstrap source notes

## Purpose

These notes capture the research spine for the biweekly AutoResearch loop. They are not the full run output; they are seed material that future runs should verify, expand, or retire.

## Source Cluster 1: ChatGPT Tasks

Public reporting around ChatGPT Tasks describes the feature as a beta scheduled-task/reminder layer that can run one-time or recurring prompts and send notifications. The practical lesson for this project is to treat Tasks as cadence infrastructure, not as the whole autonomous research engine.

Working implication:

- Use ChatGPT Tasks to trigger a bounded research loop.
- Store durable state in GitHub/Ponder/Notion-like systems.
- Escalate to Agent Mode or Deep Research for heavy work.
- Keep the scheduled task bounded enough to succeed.

## Source Cluster 2: AutoResearch-style loops

### Karpathy-style AutoResearch pattern

Working understanding:

- A model proposes changes to a research artifact.
- The system executes a bounded experiment.
- A scalar benchmark or objective evaluates whether the change improved results.
- The loop keeps or rejects the change and tries again.

Transfer to personal AI OS:

- The benchmark cannot be only model loss or validation score.
- It should become behavior change, artifact quality, workflow compounding, and doctrine improvement.

### Bilevel AutoResearch

Key idea:

- The outer loop improves the inner research loop itself.
- The inner loop optimizes a task.
- The outer loop changes the search strategy/mechanism.

Transfer:

- Every 3 runs, evaluate not only the findings but the research loop.
- Every 6 runs, update the governance layer.
- Add new search mechanisms when progress stalls.

### Sibyl-AutoResearch

Key idea:

- Autonomous research needs trial-and-error harnesses, not just paper/report generation.
- Useful failures should be captured and routed into future behavior.
- Trial signals must convert into later research actions.

Transfer:

- The AI OS loop should preserve failed experiments and rejected ideas with reasons.
- Failure classes should modify later prompts, retrieval policy, and compaction.

### AutoResearch-RL

Key idea:

- Separate frozen environment, mutable target artifact, and meta-learner/trajectory.

Transfer:

- Frozen environment: governance spec, eval rubric, source hierarchy.
- Mutable target: prompts, workflows, Ponder canvases, policies.
- Meta-learner/trajectory: run ledger, state file, decision traces.

### GEAR / population-based AutoResearch

Key idea:

- Keep multiple promising research states instead of collapsing onto one local optimum.
- Use productivity, novelty, and coverage to select paths.

Transfer:

- Maintain multiple active hypotheses in STATE.md.
- Do not prematurely compact all findings into one doctrine.
- Preserve parallel experiments.

## Source Cluster 3: High-leverage task portfolio

The strongest recurring Tasks are not reminders. They are compounding loops.

Best candidates:

1. Biweekly AI OS AutoResearch Doctrine Upgrade.
2. Weekly Ponder Canvas Audit.
3. Monthly Prompt/Workflow Version-Control Audit.
4. Monthly Decision Trace Review.
5. Quarterly AI OS Governance Audit.

Avoid:

- generic AI news briefings,
- generic productivity tips,
- tasks with no state source,
- tasks with no writeback target,
- tasks that cannot be evaluated.

## Source Cluster 4: Governance principle

A recurring AI task compounds only when it updates one of:

- doctrine,
- policy,
- prompt,
- workflow,
- experiment,
- evaluation harness,
- decision trace,
- source-of-truth memory.

Otherwise it is just a newsletter.

## Next-source queue

Future runs should verify and expand:

- Andrej Karpathy original AutoResearch material.
- Bilevel Autoresearch paper.
- Sibyl-AutoResearch paper and GitHub repo.
- AutoResearch-RL paper.
- GEAR paper.
- R&D-Agent and adjacent researcher/developer loops.
- OpenAI official ChatGPT Tasks docs if accessible.
- Community examples of high-leverage Tasks.
- Notion database automation patterns for AI run ledgers.
