---
tags:
  - type/dashboard
---

# 📆 My Month

> Monthly overview — projects, goals, finance, learning.

## This Month's Goals
> Edit these at the start of each month.

1. 
2. 
3. 

## Active Projects

```dataview
TABLE WITHOUT ID
  link(file.path, regexreplace(file.folder, ".*/", "")) AS "Project",
  status AS "Status",
  target AS "Target Date",
  area AS "Area"
FROM "01-Projects"
WHERE type = "project" AND status = "active"
SORT target ASC
```

## Tasks Due This Month

```dataview
TASK
WHERE !completed
  AND due != null
  AND due.month = date(today).month
  AND due.year = date(today).year
SORT due ASC
```

## ⏳ Scheduled This Month
> Tasks with a scheduled (start) date this month, whether or not they have a due date.

```dataview
TASK
WHERE !completed
  AND scheduled != null
  AND scheduled.month = date(today).month
  AND scheduled.year = date(today).year
SORT scheduled ASC
```

## Monthly Review

> Go to `07-Monthly-Notes/` for your monthly reviews.
> Create one: `Cmd/Ctrl + P` → "Insert template" → `tpl-monthly-review`.

## Notes Created This Month

```dataview
TABLE WITHOUT ID
  file.link AS "Note",
  file.folder AS "Location",
  file.cday AS "Created"
FROM ""
WHERE file.cday.month = date(today).month
  AND file.cday.year = date(today).year
  AND file.name != ".gitkeep"
  AND !contains(file.folder, "98-Templates")
  AND !contains(file.folder, "11-Dashboards")
SORT file.cday DESC
LIMIT 20
```
