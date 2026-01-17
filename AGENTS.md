# Agent Guardrails for House Finch Scheduling

This repository uses the **Beads methodology** for backlog management. All agents must follow these rules.

## Non-Negotiables

- `beads/backlog.jsonl` is **append-only** — never modify, rewrite, reorder, or delete existing lines
- **Humans should not edit `backlog.jsonl` directly** — all changes are agent-driven
- When outputting backlog changes, provide **only the new JSONL lines to append**
- Every new item must have a **unique ID** following conventions (`EPIC-N`, `ISSUE-N.M`)
- Issues must reference an **existing epic** by ID
- Each line must be **valid JSON**

## Before Making Backlog Changes

1. Read the full current `beads/backlog.jsonl` for context
2. Use the prompt template: [.beads/prompts/backlog-change-template.md](.beads/prompts/backlog-change-template.md)
3. Output only new lines to append — never rewrite existing content

## Documentation

| Topic | Location |
|-------|----------|
| Operating rules | [.beads/operating-rules.md](.beads/operating-rules.md) |
| Backlog format & IDs | [.beads/backlog-format.md](.beads/backlog-format.md) |
| Project context | [.beads/context.md](.beads/context.md) |
| Workflow for proposals | [.beads/workflow.md](.beads/workflow.md) |
| Validation requirements | [.beads/validation.md](.beads/validation.md) |
