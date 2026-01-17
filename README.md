# House Finch Scheduling & Subscriptions

This repository contains the planning backlog and supporting artifacts for building a **customer-facing scheduling, subscription, and hours-tracking system** for **The House Finch**.

The goal is to allow customers to:
- Log in on the House Finch website
- View their remaining (“banked”) organizing hours
- Schedule organizing appointments directly on the site
- Purchase additional hours easily

And to allow staff to:
- Receive real-time notifications when appointments are scheduled
- View schedules and customer balances in a centralized dashboard
- Eliminate reliance on Connecteam for scheduling workflows

---

## Project Philosophy

This project follows **Steve Yegge’s Beads methodology**:

- Problems are identified *before* solutions
- Work is broken into small, incremental, testable beads
- The backlog is the primary planning artifact

Reference:  
https://github.com/steveyegge/beads

---

## Repository Structure

```text
.
├── beads/
│   └── backlog.jsonl   # Beads-style backlog (source of truth)
└── README.md           # This file
```

---

## Agent Guardrails

For authoritative rules on working with this backlog, see [`AGENTS.md`](AGENTS.md).

Detailed documentation lives in [`.beads/`](.beads/):
- [Operating rules](.beads/operating-rules.md)
- [Backlog format](.beads/backlog-format.md)
- [Project context](.beads/context.md)
- [Workflow](.beads/workflow.md)
- [Validation](.beads/validation.md)
- [Prompt templates](.beads/prompts/backlog-change-template.md)

---

## Updating the Backlog (Agent-Driven Only)

The file `beads/backlog.jsonl` is the **system of record** for this project’s backlog.  
It is **not intended to be edited directly by humans**.

All changes to the backlog — including adding new epics, issues, or refining existing ones — should be performed **by AI agents** using structured prompts.

### Why humans should not edit `backlog.jsonl`

- The file is intentionally **append-only** and line-oriented (JSONL)
- Manual edits increase the risk of:
  - Invalid JSON
  - Broken references between epics and issues
  - Inconsistent IDs or formats
- Agents can reason about dependencies, scope, and duplication more reliably when given full context

---

## How to Prompt an Agent to Add Backlog Items

When you want to create new backlog items, **always provide the current `backlog.jsonl` file as input context** to the agent.

Then issue a prompt like one of the following:

### Example: Add a New Epic

```text
You are an agent managing a Beads-style backlog.

Here is the current contents of beads/backlog.jsonl:
<PASTE FULL backlog.jsonl HERE>

Add a new epic for:
"Customer appointment cancellations and rescheduling"

Requirements:
- Follow the existing epic format exactly
- Generate a new unique EPIC ID
- Append the epic as a new JSONL line
- Do not modify existing lines
- Output only the new JSONL line
```
