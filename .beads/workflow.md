# Workflow for Proposing Backlog Items

## End-to-End Process

```
Request → Agent generates JSONL → PR created → Human review → Merge
```

### 1. Request

A stakeholder or developer describes the desired backlog change:
- New epic needed
- New issues under an existing epic
- Status update for existing items

### 2. Agent Generates JSONL

The agent:
1. Reads the current `beads/backlog.jsonl` for full context
2. Uses the [prompt template](.beads/prompts/backlog-change-template.md)
3. Generates **only the new JSONL lines** to append
4. Validates the output against [format rules](backlog-format.md)

### 3. PR Created

The new lines are added to the end of `beads/backlog.jsonl`:
- Append after the last line
- Add a blank line before a new epic (for readability)
- Never modify existing lines

### 4. Human Review

Reviewer checks:
- [ ] IDs are unique and follow conventions
- [ ] Issues reference existing epics
- [ ] Each line is valid JSON
- [ ] Acceptance criteria are clear and testable
- [ ] No existing lines were modified

### 5. Merge

Once approved, merge the PR. If EPIC-8 visualization is implemented, the static site will regenerate automatically.

## Where to Add New Lines

Always **append** to the end of `beads/backlog.jsonl`:

```
[existing content]
[blank line if starting new epic]
{"type":"epic","id":"EPIC-10",...}
{"type":"issue","epic":"EPIC-10","id":"ISSUE-10.1",...}
```

## Status Updates

To mark an item as completed or change its status:
- Append a new line with the same ID and updated `status`
- Include all original fields plus the new status
- The latest entry for an ID is authoritative
