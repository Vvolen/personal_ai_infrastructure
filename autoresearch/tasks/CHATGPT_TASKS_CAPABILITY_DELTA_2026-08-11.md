# ChatGPT Tasks Capability Delta — 2026-08-11

Status: current capability note; proposed input to next task-policy audit

## Why this exists

`HIGH_LEVERAGE_CHATGPT_TASKS.md` was written on 2026-06-02 and contains bootstrap assumptions that have changed. This delta preserves the original playbook while recording current verified product behavior before the next formal policy update.

## Verified current facts

As of 2026-08-11, OpenAI documents Scheduled Tasks as supporting one-off, recurring, and monitoring work. Monitoring tasks remember previous runs and may stop when an end condition is met.

Current plan limits are documented as:
- Go: 3 active tasks
- Plus: 5
- Business/Edu: 10
- Pro/Enterprise: 15

Tasks cannot run more than once per hour, and unattended tasks may automatically pause after inactivity.

A scheduled task created in a Project that has files cannot access those Project-uploaded files. Therefore a file-backed governed run must re-read canonical state through a connector, repository, or other accessible state source rather than assuming Project files will be present.

Voice chats and GPTs are not supported within Scheduled Tasks.

OpenAI separately documents Workspace Agents for eligible Business/Enterprise workspaces. Workspace Agents can carry reusable instructions, tools, apps, custom MCPs, skills and files, run on a schedule, and be triggered through an API. The current API-trigger path queues work with `202 Accepted` but does not return a run ID or provide the agent response through the API, so it should not be treated as a complete durable orchestration protocol by itself.

## Policy consequence

Keep the existing architectural separation:

```text
Scheduled Task
  trigger / monitor / report
          ↓
Canonical state preflight
  GitHub / explicit ledger
          ↓
Durable execution surface
  Hermes / Work / eligible Workspace Agent / Codex workflow
          ↓
Artifact + trace + evaluator
          ↓
Reviewable writeback
```

## Revised task quality contract

A recurring governed task is valid only if it has:

1. a canonical state source that the runtime can actually read;
2. a bounded scope and explicit stop condition;
3. an output artifact, not only a notification;
4. an evaluation or acceptance rule;
5. a writeback or review target;
6. a policy for what happens when state is inaccessible;
7. a distinction between trigger state and durable workflow state.

## Implication for T001 AutoResearch

T001 remains high leverage, but the current failure mode is now concrete: prior scheduled runs produced useful output without updating GitHub. T001 should therefore be considered incomplete unless it either:

- creates a reviewable GitHub PR containing the run + state/ledger diffs, or
- emits a manifest that an explicit downstream writeback workflow commits.

## Primary sources

- OpenAI Help Center, "Scheduled Tasks in ChatGPT," current as of 2026-08-11: https://help.openai.com/en/articles/10291617-scheduled-tasks-in-chatgpt
- OpenAI Help Center, "ChatGPT Workspace Agents for Enterprise and Business," current as of 2026-08-11: https://help.openai.com/en/articles/20001143/
