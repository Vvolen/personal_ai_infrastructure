# ChatGPT Context & Workspace Capability Delta — 2026-08-25

Status: current capability note  
Linked run: `autoresearch/runs/2026-08-25_run_004.md`

## Verified changes since Run 003

### Project memory is now switchable
On 2026-08-14 OpenAI documented that eligible existing projects can switch between default and project-only memory.

Project-only memory:
- can use conversations within the same project;
- does not reference memories/conversations outside the project;
- keeps project information out of outside-chat memory;
- disables ChatGPT Work inside that project.

Policy implication:
Project-only memory is an isolation tool, not a replacement for canonical state. Work-backed governed projects should load GitHub/ledger state explicitly.

### Computer History for macOS
On 2026-08-13 OpenAI introduced Computer History for macOS.

It:
- can let ChatGPT/Codex reference selected app/site interaction events;
- is off by default;
- is user-inspectable/deletable;
- does not record screenshots, screen recordings, microphone input, or system audio.

Policy implication:
Treat as ambient context reinstatement/source-location memory, not authority for durable facts, decisions, or doctrine.

### Google Drive in Library
Connected Drive files/folders can now be browsed from Library and used in Chat/Work while remaining linked to the Drive source.

Policy implication:
Prefer source-linked references over unnecessary document duplication when the connector provides sufficient freshness and provenance.

### Scheduled Tasks
No architectural boundary change was found:
- Tasks remain one-off / recurring / monitoring triggers.
- Project-uploaded files are still unavailable to scheduled tasks.
- The dedicated Scheduled page improves operation but does not make task history canonical state.

### Ponder
Ponder's public beta still centers on persistent interactive tools, plans, tracking, multi-surface work, collaborative agents, and execution tracking.

No public developer/runtime API surfaced in this scan.

Policy implication:
Keep Ponder in the cognitive-cockpit layer and compare it with the increasingly stateful native ChatGPT workspace.

## Revised E007 comparison

Old:
Ponder vs ChatGPT Site.

New:
Ponder interactive artifact vs ChatGPT Project + Site + Computer History, with GitHub as shared canonical state.

## Sources

- https://help.openai.com/en/articles/6825453
- https://help.openai.com/en/articles/10169521-projects-in-chatgpt
- https://help.openai.com/en/articles/10291617
- https://ponder.do/
- https://ponder.do/faq
