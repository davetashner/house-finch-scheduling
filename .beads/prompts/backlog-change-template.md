# Backlog Change Prompt Template

Use this template when asking an agent to add items to the backlog.

---

## Template: Add New Epic

```
You are an agent managing a Beads-style backlog.

Rules:
- Output ONLY the new JSONL lines to append
- Never modify existing lines
- Use unique IDs (next available EPIC-N)
- Follow the exact format of existing entries
- Set status to "open" for new items

Here is the current contents of beads/backlog.jsonl:

<PASTE FULL backlog.jsonl HERE>

Add a new epic for:
"<DESCRIBE THE EPIC>"

Include 3-5 issues that break down this epic into actionable work items.
```

---

## Template: Add Issues to Existing Epic

```
You are an agent managing a Beads-style backlog.

Rules:
- Output ONLY the new JSONL lines to append
- Never modify existing lines
- Use unique IDs (ISSUE-N.M where N matches epic number)
- Follow the exact format of existing entries
- Set status to "open" for new items
- Each issue needs clear acceptance criteria

Here is the current contents of beads/backlog.jsonl:

<PASTE FULL backlog.jsonl HERE>

Add new issues under EPIC-<N> for:
"<DESCRIBE THE WORK TO BE DONE>"
```

---

## Template: Update Item Status

```
You are an agent managing a Beads-style backlog.

Rules:
- Output ONLY the new JSONL line to append
- This is an append-only update (original line stays, new line supersedes)
- Include all original fields plus the updated status

Here is the current contents of beads/backlog.jsonl:

<PASTE FULL backlog.jsonl HERE>

Update the status of <ITEM-ID> to "<NEW-STATUS>".
```

---

## Checklist Before Submitting Agent Output

- [ ] Output contains only new JSONL lines (no modifications)
- [ ] Each line is valid JSON
- [ ] IDs are unique and follow conventions
- [ ] Issues reference existing epics
- [ ] Acceptance criteria are specific and testable
