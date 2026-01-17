# Backlog Format & ID Conventions

## File Format

`beads/backlog.jsonl` uses JSON Lines format:
- One JSON object per line
- Blank lines are allowed for visual grouping (between epics)
- No trailing commas

## Epic Schema

```json
{
  "type": "epic",
  "id": "EPIC-N",
  "title": "Short descriptive title",
  "intent": "What this epic aims to achieve",
  "status": "open"
}
```

### Required Fields

| Field | Type | Description |
|-------|------|-------------|
| `type` | string | Always `"epic"` |
| `id` | string | Unique identifier: `EPIC-N` where N is a positive integer |
| `title` | string | Brief, descriptive title |
| `intent` | string | The goal or purpose of the epic |
| `status` | string | Current status (see below) |

## Issue Schema

```json
{
  "type": "issue",
  "epic": "EPIC-N",
  "id": "ISSUE-N.M",
  "title": "Short descriptive title",
  "description": "Detailed description of the work",
  "acceptance": ["Criterion 1", "Criterion 2"],
  "status": "open"
}
```

### Required Fields

| Field | Type | Description |
|-------|------|-------------|
| `type` | string | Always `"issue"` |
| `epic` | string | Parent epic ID (must exist in backlog) |
| `id` | string | Unique identifier: `ISSUE-N.M` |
| `title` | string | Brief, descriptive title |
| `description` | string | Detailed explanation of the work |
| `acceptance` | array | List of acceptance criteria (strings) |
| `status` | string | Current status (see below) |

## ID Conventions

### Epics
- Format: `EPIC-N` where N is a positive integer
- Assign the next available number (max existing + 1)
- Example: If `EPIC-9` exists, next epic is `EPIC-10`

### Issues
- Format: `ISSUE-N.M` where:
  - `N` matches the parent epic number
  - `M` is a positive integer, incrementing within the epic
- Example: Issues under `EPIC-3` are `ISSUE-3.1`, `ISSUE-3.2`, etc.

## Status Values

| Status | Meaning |
|--------|---------|
| `open` | Not yet started |
| `in-progress` | Currently being worked on |
| `done` | Completed |
| `blocked` | Cannot proceed due to dependency |
