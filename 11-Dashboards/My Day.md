---
tags:
  - type/dashboard
---

# ☀️ My Day

> What's on your plate today.

## Today's Daily Note

> `Cmd/Ctrl + P` → "Open today's daily note" to create or open it.

## Tasks Due Today

```dataview
TASK
WHERE !completed
  AND due = date(today)
SORT priority DESC
```

## Tasks Scheduled for Today

```dataview
TASK
WHERE !completed
  AND scheduled = date(today)
SORT priority DESC
```

## Overdue Tasks

```dataview
TASK
WHERE !completed
  AND due < date(today)
  AND due != null
SORT due ASC
```

## 📓 From Today's Note
> Any open task written in today's daily note, due date or not.

```dataview
TASK
FROM "05-Daily-Notes"
WHERE !completed AND file.day = date(today)
```

## Waiting For

```dataview
TASK
WHERE status = "w"
  AND !completed
SORT file.name ASC
```

## Today's Notes

```dataview
TABLE WITHOUT ID
  file.link AS "Note",
  file.folder AS "Location"
FROM ""
WHERE file.cday = date(today)
  AND file.name != ".gitkeep"
  AND !contains(file.folder, "98-Templates")
  AND !contains(file.folder, "11-Dashboards")
SORT file.ctime DESC
```
