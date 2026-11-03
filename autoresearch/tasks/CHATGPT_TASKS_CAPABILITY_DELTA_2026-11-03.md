# ChatGPT Tasks capability delta — 2026-11-03
Status: capability note, not doctrine promotion.

Official source checked Nov 3: https://help.openai.com/en/articles/10291617-scheduled-tasks-in-chatgpt

- One-off, recurring, monitoring and event-triggered Tasks available for eligible users; event-triggered GitHub/Gmail/Slack tasks execute in Work and require specific authorized events and conditions.
- A Task created inside a Project cannot access uploaded/stored Project files.
- Current documented active task limits: Free/Go 3, Plus 5, Business/Edu 10, Pro/Enterprise 15; access depends on plan/app/workspace.
- App connection does not itself create a task or authorize a new action. Review trigger, condition, prompt and approval flow.

Proposed, **not created**: a narrowly scoped GitHub PR-event *read-only* reconciliation Task that checks `state`, `draft`, `merged`, head SHA, and review decision against `STATE.md` assertions and drafts a reconciliation receipt. This Run observed the branch's Oct 7 snapshot describing PR #2 as draft while the Nov 3 GitHub API returned `draft=false, state=open, merged=false`. Ready-for-review does not authorize merge or doctrine promotion. Tasks remain triggers, never canonical governance state.
