# ChatGPT Native Agentic OS Delta — 2026-10-06

Status: capability note  
Linked run: `autoresearch/runs/2026-10-06_run_007.md`

## New Native Stack

As of the 2026-09-29 product wave:

### Dot
Persistent always-on agent with:
- a durable goal/responsibility;
- connected apps;
- its own cloud computer;
- memory/context for ongoing work;
- autonomy controls;
- ability to create Work/Codex tasks and use Codex cloud environments where available.

### Space + Pages
Durable collaborative artifact layer:
- pages;
- files;
- direct editing;
- comments/collaboration;
- ChatGPT-assisted revision;
- interactive content.

### Sites + Automations
Published interactive surfaces can now own recurring cloud schedules.

### Codex Cloud
Reusable repository/tool/dependency environments with an isolated workspace per task.

### Scheduled Tasks
Remain the trigger layer:
- one-off;
- recurring;
- monitoring;
- event-triggered Work flows where supported.

## Architectural Mapping

```text
Tasks / events
  = trigger layer

Dot
  = persistent responsibility / attention owner

Space + Pages / Site
  = cognitive workspace / projection layer

Work / Codex
  = execution layer

Codex Cloud
  = isolated execution substrate

GitHub / DB
  = canonical governance + durable structured state
```

## Implications

1. Native ChatGPT can now prototype much of the intended AI OS without bespoke orchestration code.
2. Dot memory should not be treated as canonical doctrine.
3. Codex Cloud is a promising E011 isolation substrate.
4. E007 should compare Ponder against Dot + Space/Pages + Site over identical GitHub state.
5. Site schedules can update dashboards, but must not bypass canonical writeback/review.
6. Post-merge reconciliation is a strong event-triggered Task candidate, but this run does not create it.

## Source Notes

Official:
- https://help.openai.com/en/articles/6825453-chatgpt-release-notes
- https://help.openai.com/en/articles/20001530-getting-started-with-your-dot
- https://help.openai.com/en/articles/20001549-getting-started-with-space-in-chatgpt
- https://help.openai.com/en/articles/20001339-creating-and-using-chatgpt-sites
- https://help.openai.com/en/articles/10291617-scheduled-tasks-in-chatgpt
