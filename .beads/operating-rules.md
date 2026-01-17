# Beads Operating Rules

These rules govern how agents interact with `beads/backlog.jsonl`.

## MUST

- Treat `beads/backlog.jsonl` as **append-only**
- Generate **unique IDs** for new items (check existing IDs first)
- Ensure issues reference an **existing epic** by ID
- Output **only new JSONL lines** when making changes
- Preserve the existing format exactly (field order, naming, structure)
- Parse and validate JSON before proposing additions

## MUST NOT

- Modify, rewrite, or reorder existing lines
- Delete any lines from the backlog
- Create duplicate IDs
- Reference non-existent epics in issues
- Assume the backlog structure — always read it first

## Correcting Errors

If a previously added line contains an error:
- **Do not edit the original line**
- Append a new corrective line that supersedes the erroneous one
- Add a note in the `description` field explaining it replaces a prior entry
- Consider adding a `supersedes` field referencing the original ID

## Human Participation

Humans should not directly edit `beads/backlog.jsonl`. Instead:
1. Describe the desired change to an agent
2. Agent generates the JSONL lines
3. Human reviews and merges via PR
