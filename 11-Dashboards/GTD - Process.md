---
tags:
  - type/dashboard
---

# 📥 GTD — Process Inbox

> Work through each item in your inbox using the GTD decision tree.

## The GTD Decision Tree

For each item in your inbox, ask:

```
1. What is it?
2. Is it actionable?
   ├── NO → Delete, file in Resources, or tag #someday
   └── YES → What's the next action?
       ├── Takes < 2 minutes? → DO IT NOW
       ├── Should someone else do it? → DELEGATE (create Waiting task)
       └── Takes > 2 minutes? → DEFER
           ├── Specific date? → Add 📅 due date
           └── No date? → Add to project or Next Actions with #context/
```

## Unprocessed Inbox Items

```dataview
TABLE WITHOUT ID
  file.link AS "Item",
  file.cday AS "Captured"
FROM "00-Inbox"
WHERE file.name != ".gitkeep" AND file.name != "Welcome to Your Vault"
SORT file.cday ASC
```

## Processing Actions

After clarifying each inbox item:

| Action | What to do |
|--------|-----------|
| **Delete** | Not useful → delete the note |
| **Reference** | Useful info → move to `03-Resources/` |
| **Someday/Maybe** | Interesting but not now → add `#someday` tag, move to `03-Resources/` |
| **Project** | Multi-step outcome → create folder in `01-Projects/`, use `tpl-project` |
| **Next Action** | Single task → add to relevant project/area note with `#context/` tag |
| **Waiting** | Delegated → create `- [w]` task noting who |
| **Calendar** | Date-specific → add task with `📅 YYYY-MM-DD` |

## Quick Capture Reminders

- **2-Minute Rule**: If it takes less than 2 minutes, do it NOW. Don't capture it.
- **Capture everything**: Don't filter at capture time. Inbox is for raw input.
- **Process daily**: Aim to empty your inbox at least once a day.
- **One item at a time**: Don't skip around. Go top to bottom.

## All Someday/Maybe Items

```dataview
TABLE WITHOUT ID
  file.link AS "Item",
  file.folder AS "Location"
FROM #someday
SORT file.name ASC
```

## All Waiting For

```dataview
TASK
WHERE status.symbol = "w"
  AND !completed
SORT file.name ASC
```
