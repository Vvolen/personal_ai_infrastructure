# Biweekly AutoResearch Governance Loop

Created: 2026-06-02
Timezone: America/Phoenix
Cadence: every 14 days
Status: bootstrap specification

## 0. Purpose

This is a recurring research-and-compounding loop for upgrading a personal AI operating system.

It is inspired by Karpathy-style AutoResearch, but adapted for everyday AI leverage rather than only benchmark optimization. The loop should not merely summarize AI news. It should improve the user’s actual operating doctrine, prompts, workflows, policies, retrieval strategies, evaluation harnesses, and tool use.

The core idea is simple:

> Every run reads prior runs, compacts durable signal, researches the frontier, identifies hidden unlocks, updates the operating doctrine, proposes experiments, and leaves the next run better-positioned than the last.

## 1. North Star

Create a self-compounding AI leverage system that materially improves how the user thinks, asks, researches, builds, prompts, evaluates, and uses tools like ChatGPT, Ponder, GitHub, and future knowledge workspaces.

The goal is not information accumulation. The goal is capability compounding.

Each run should answer:

1. What changed since the last run?
2. What did the previous run miss?
3. What has become more important?
4. What should be retired, compacted, or downgraded?
5. What new operating policy, primitive, framework, prompt, workflow, or experiment should be adopted?
6. What would a top 0.1% AI operator do next?

## 2. Storage Model

Issues are disabled in this repository, so this folder acts as the GitHub control plane.

Recommended structure:

```text
autoresearch/
  BIWEEKLY_AUTORESEARCH_GOVERNANCE_LOOP.md   # this spec
  STATE.md                                   # current compacted doctrine
  RUN_LEDGER.md                              # index of runs
  policies/
    governance.md
    retrieval_policy.md
    memory_policy.md
    evaluation_policy.md
    compaction_policy.md
  prompts/
    run_prompt.md
    critic_prompt.md
    compaction_prompt.md
    hidden_unlock_prompt.md
  runs/
    2026-06-02_run_000_bootstrap.md
    2026-06-16_run_001.md
    ...
```

## 3. Run Cadence

Run every 14 days.

Suggested schedule:

- Every other Tuesday morning, America/Phoenix time.
- Each run should produce a dated artifact under `autoresearch/runs/`.
- Every 3 runs, produce a compaction update to `autoresearch/STATE.md`.
- Every 6 runs, perform a governance audit and update this spec if needed.

## 4. Inspiration: AutoResearch Pattern

The AutoResearch family of systems treats research as a loop with objective feedback.

Relevant principles from current research:

- Karpathy-style AutoResearch established a simple loop: generate research ideas, implement changes, evaluate against a measurable benchmark, keep what improves the score, iterate.
- Bilevel AutoResearch extends this by adding a meta-loop that improves the research loop itself. The outer loop generates new search mechanisms, while the inner loop optimizes the actual task.
- Adjacent systems such as R&D-Agent separate researcher and developer roles, run multiple exploration traces, merge results, and use performance feedback to guide iteration.
- The most important transferable idea is not “let an agent run forever.” It is: define an objective, preserve traces, evaluate results, compact durable signal, and change the search strategy when progress stalls.

For this personal AI loop, the measurable objective is not a model benchmark. It is operating-system improvement.

## 5. Core Loop

Each biweekly run follows this sequence:

1. Read previous state.
2. Read the most recent 1-3 run artifacts.
3. Compact prior findings into current doctrine.
4. Identify stale assumptions and open hypotheses.
5. Generate research questions for this run.
6. Search the frontier using a source hierarchy.
7. Extract frameworks, patterns, and examples.
8. Compare new findings against existing doctrine.
9. Surface hidden unlocks.
10. Propose concrete experiments for the next 14 days.
11. Score the run.
12. Update run ledger and next-run queue.

## 6. Source Hierarchy

Prefer sources in this order:

1. Primary papers, official docs, repos, changelogs.
2. Engineering blogs from credible labs or builders.
3. Practitioner writeups with implementation detail.
4. Reputable company research posts.
5. Forum posts or social sources only if they point to primary artifacts.
6. SEO summaries only as weak discovery hints, never as final authority.

## 7. Research Scope

Each run should scan for frontier progress in:

- AutoResearch and meta-autoresearch.
- Autonomous research loops.
- Cognitive engineering.
- Context engineering.
- Agentic RAG and dynamic retrieval.
- Memory engineering and context graphs.
- Multi-agent orchestration.
- Evaluation-driven development for agents.
- Meta-evaluation and judge calibration.
- Prompt/context governance.
- Tool-use patterns with GitHub, Notion-like systems, Ponder, Exa, Tavily, and ChatGPT.
- Human-AI workflows used by elite operators.

## 8. Governance Layer

Every run must enforce these policies.

### 8.1 Evidence Policy

Every important claim should be marked as one of:

- Fact: directly supported by a cited source.
- Inference: reasoned conclusion based on sources.
- Speculation: plausible but not yet validated.
- Recommendation: proposed action.

No major operating change should be accepted unless it has either:

- direct evidence,
- a strong inference chain,
- or a small proposed experiment.

### 8.2 Retrieval Policy

Use retrieval deliberately.

Start broad, then narrow:

1. Semantic discovery for surprising or non-obvious sources.
2. Targeted search for primary sources.
3. Extraction of full source content when snippets are insufficient.
4. Cross-checking of high-impact claims.

Budget defaults:

- Discovery queries: max 6.
- Primary source reads: max 10.
- Deep extraction: max 5.
- Stop when the run has enough evidence to change doctrine or when the remaining uncertainty is clearly documented.

Search again only when:

- a core claim is unsupported,
- current sources conflict,
- a key paper/repo/docs page has not been read,
- a finding would materially change the user’s operating system,
- or the run explicitly identifies an evidence gap.

### 8.3 Compaction Policy

After every 3 runs:

- preserve durable principles,
- keep only high-leverage prompts,
- extract reusable frameworks,
- collapse repeated observations,
- mark dead ends,
- archive low-confidence ideas,
- update `STATE.md` with the current doctrine.

Never compact away:

- decision traces,
- rejected hypotheses with useful failure reasons,
- evaluation results,
- operating policies,
- or source provenance.

### 8.4 Memory Policy

Each durable insight should be stored with metadata:

```yaml
id: unique identifier
type: principle | prompt | workflow | policy | experiment | failure_mode | source | hypothesis | decision
status: proposed | active | retired | rejected | needs_validation
confidence: low | medium | high
source_refs: []
created_at: YYYY-MM-DD
last_reviewed: YYYY-MM-DD
linked_runs: []
next_action: string
```

### 8.5 Evaluation Policy

Score every run from 1-5 on:

- Novelty: did it find something meaningfully new?
- Actionability: can the user apply it immediately?
- Evidence quality: are claims grounded?
- Doctrine improvement: did it update operating policy?
- Compounding value: will future runs be better because this run happened?
- Integration readiness: can it be used in Ponder/ChatGPT/GitHub workflows?

A successful run is not “interesting.” A successful run changes behavior.

### 8.6 Anti-Slop Policy

Reject:

- generic AI productivity advice,
- vague “use agents better” claims,
- unsourced hype,
- long lists without implementation steps,
- repeated frameworks with new names but no new function,
- recommendations that cannot be tested.

Every output must include:

- an operating upgrade,
- an experiment,
- a policy update,
- or a reusable artifact.

## 9. Run Output Template

Each run should produce:

```markdown
# AutoResearch Run YYYY-MM-DD

## 1. Previous-State Readout
- Current doctrine:
- Active hypotheses:
- Recent experiments:
- Known gaps:

## 2. What Changed Since Last Run
- New sources:
- New methods:
- New risks:
- New opportunities:

## 3. Frontier Scan
- AutoResearch:
- Cognitive/context engineering:
- Agentic retrieval:
- Memory/context graphs:
- Evaluation/meta-evaluation:
- Tooling/workflow:

## 4. Hidden Unlocks
For each:
- Unlock:
- Why it matters:
- What most users miss:
- What top 0.1% operators do:
- Small experiment:

## 5. Doctrine Updates
- Add:
- Modify:
- Retire:
- Needs validation:

## 6. New Artifacts
- Prompts:
- Policies:
- Workflows:
- Ponder canvas patterns:
- GitHub/Notion structures:

## 7. Experiments for Next 14 Days
- Experiment:
- Success metric:
- Evaluation plan:
- Expected output:

## 8. Decision Trace
- Inputs considered:
- Sources used:
- Assumptions:
- Tradeoffs:
- Decisions:
- Rejected paths:

## 9. Run Score
- Novelty:
- Actionability:
- Evidence:
- Doctrine improvement:
- Compounding value:
- Integration readiness:

## 10. Next-Run Queue
- Questions:
- Sources to revisit:
- Experiments to evaluate:
- Suspected hidden unlocks:
```

## 10. Bootstrap Run Prompt

Use this prompt to initiate the first or next run.

```text
Act as an AutoResearch governance agent for a personal AI operating system.

Your job is to run a biweekly research-and-compounding cycle that improves how I use AI every day.

First, read the current AutoResearch state, the previous run artifacts, and the governance policies. Then research what has changed in AI workflow design, cognitive engineering, context engineering, memory engineering, agentic retrieval, evaluation loops, and autoresearch systems since the last run.

Pay special attention to:
- Karpathy-style AutoResearch.
- Bilevel AutoResearch and meta-autoresearch.
- R&D-Agent and adjacent researcher/developer loops.
- AutoResearch systems with persistent memory.
- Agentic RAG and dynamic retrieval.
- Context graphs and decision traces.
- Evaluation-driven agent development.
- Meta-evaluation and judge calibration.
- Practical workflows for Ponder, ChatGPT, GitHub, and Notion-like systems.

Run the governed loop:
1. Read previous state.
2. Compact the current doctrine.
3. Identify stale assumptions.
4. Generate research hypotheses.
5. Search using the source hierarchy.
6. Extract actionable frameworks.
7. Compare findings against current doctrine.
8. Surface hidden unlocks.
9. Propose experiments.
10. Update the run ledger and next-run queue.

Use this evidence taxonomy:
- Fact: source-backed.
- Inference: reasoned from sources.
- Speculation: plausible but unvalidated.
- Recommendation: proposed action.

Quality bar:
This should improve how I use AI every day. Do not merely summarize AI news. Produce policies, primitives, prompts, workflows, experiments, and decision traces.
```

## 11. Automation Path

There are three implementation levels.

### Level 1: Manual But Compounding

Every two weeks, run the bootstrap prompt in ChatGPT or Ponder, pointing it to this folder and the most recent run artifacts. Commit the result under `autoresearch/runs/`.

This is immediately usable.

### Level 2: Semi-Automated GitHub Control Plane

Use GitHub as the memory layer:

- Store state in `STATE.md`.
- Store run logs in `runs/`.
- Store policies in `policies/`.
- Store prompts in `prompts/`.
- Use commits as decision history.

This is robust and auditable.

### Level 3: Scheduled GitHub Action

A GitHub Action could run every 14 days, call an LLM/research API, read prior files, generate a new run artifact, and open a pull request.

This requires API keys and a script. It should not be fully automated until the manual loop has produced at least 3 good runs and the evaluation rubric is calibrated.

Recommended safety gate:

- The Action creates a PR, not a direct commit.
- The PR includes run output and doctrine changes.
- Human reviews before merge.
- The agent cannot overwrite policies without explicit diff review.

## 12. First 3 Runs

### Run 000: Bootstrap

Goals:
- establish doctrine,
- research Karpathy-style AutoResearch and adjacent systems,
- define evaluation rubric,
- propose first experiments.

### Run 001: Integration

Goals:
- test the first experiments,
- create Ponder canvas patterns,
- identify which outputs actually changed user behavior,
- refine retrieval and compaction policies.

### Run 002: Meta-Optimization

Goals:
- evaluate the loop itself,
- identify bottlenecks,
- modify the governance layer,
- compact the first three runs into `STATE.md`.

## 13. Operating Principle

The task is not “research AI.”

The task is to build a self-compounding intelligence layer around the user’s AI usage.

Every run should leave behind a better map, a better question, a better prompt, a better policy, a better experiment, or a better way of thinking.
