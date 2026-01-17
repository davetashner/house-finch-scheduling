# Backlog Validation Requirements

Agents and tools must ensure all additions to `beads/backlog.jsonl` meet these requirements.

## JSON Validity

- [ ] Each non-blank line parses as valid JSON
- [ ] No trailing commas in objects or arrays
- [ ] Strings are properly quoted and escaped

## Required Fields

### For Epics
- [ ] `type` equals `"epic"`
- [ ] `id` is present and matches `EPIC-N` pattern
- [ ] `title` is a non-empty string
- [ ] `intent` is a non-empty string
- [ ] `status` is a valid status value

### For Issues
- [ ] `type` equals `"issue"`
- [ ] `epic` references an existing epic ID
- [ ] `id` is present and matches `ISSUE-N.M` pattern
- [ ] `title` is a non-empty string
- [ ] `description` is a non-empty string
- [ ] `acceptance` is an array of strings (at least one)
- [ ] `status` is a valid status value

## ID Rules

- [ ] All IDs are unique across the entire file
- [ ] Epic IDs follow `EPIC-N` format (N = positive integer)
- [ ] Issue IDs follow `ISSUE-N.M` format where N matches parent epic
- [ ] New IDs use the next available number (no gaps required, but no duplicates)

## Reference Integrity

- [ ] Every issue's `epic` field references an existing `EPIC-N` ID
- [ ] The referenced epic must appear earlier in the file (or in the same batch of additions)

## Status Values

- [ ] Status is one of: `open`, `in-progress`, `done`, `blocked`

## Append-Only Constraint

- [ ] No existing lines were modified
- [ ] No lines were deleted
- [ ] No lines were reordered
- [ ] New content appears only at the end of the file
