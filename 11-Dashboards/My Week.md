---
tags:
  - type/dashboard
---

# 📅 My Week

> This week's tasks, priorities, and review.

## Tasks Due This Week

```dataview
TASK
WHERE !completed
  AND due >= date(today) - dur(date(today).weekday + "days")
  AND due < date(today) - dur(date(today).weekday + "days") + dur("7 days")
  AND due != null
SORT due ASC
GROUP BY due
```

## In Progress

```dataview
TASK
WHERE status.symbol = "/"
  AND !completed
SORT file.name ASC
```

## This Week's Priorities
> Edit these manually each Monday or during your weekly review.

1. 
2. 
3. 

## Weekly Review

> Open your latest weekly review: go to `06-Weekly-Notes/`.
> Or create one: `Cmd/Ctrl + P` → "Insert template" → `tpl-weekly-review`.

## Notes Created This Week

```dataview
TABLE WITHOUT ID
  file.link AS "Note",
  file.folder AS "Location",
  file.cday AS "Created"
FROM ""
WHERE file.cday >= date(today) - dur(date(today).weekday + "days")
  AND file.name != ".gitkeep"
  AND !contains(file.folder, "98-Templates")
  AND !contains(file.folder, "11-Dashboards")
SORT file.cday DESC
```
