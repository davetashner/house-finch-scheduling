# Project Context: House Finch Scheduling

## What We're Building

**The House Finch** is a professional organizing service. This project creates a customer-facing web system for scheduling appointments and managing subscription hours.

## Customer Goals

- **Log in** to their account on thehousefinch.com
- **View banked hours** — see how many organizing hours they've purchased
- **Schedule appointments** — book times that deduct from their balance
- **Purchase more hours** — buy additional hours through the website

## Staff Goals

- **Receive notifications** when customers book, modify, or cancel appointments
- **View all schedules** in a centralized dashboard
- **See customer balances** for planning and communication
- **Replace Connecteam** — eliminate dependency on external scheduling tool

## Major Epics Overview

| Epic | Purpose |
|------|---------|
| EPIC-1 | Customer accounts & authentication |
| EPIC-2 | Banked hours tracking (ledger) |
| EPIC-3 | Web scheduling interface |
| EPIC-4 | Staff notification system |
| EPIC-5 | Payments & purchasing hours |
| EPIC-6 | Staff dashboard |
| EPIC-7 | Retire Connecteam dependency |
| EPIC-8 | Backlog visualization (read-only) |
| EPIC-9 | Agent guardrails & configuration |

## Repository Purpose

This repo is **planning-first**. The primary artifact is `beads/backlog.jsonl`, which defines all work items using the Beads methodology. Implementation code may live here or in separate repositories as the project evolves.

## Beads Methodology

- Problems are identified before solutions
- Work is broken into small, incremental, testable pieces
- The backlog is the primary planning artifact
- Reference: https://github.com/steveyegge/beads
