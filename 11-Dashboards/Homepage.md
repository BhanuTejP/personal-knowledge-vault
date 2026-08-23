---
tags:
  - type/dashboard
---

# 🏠 Homepage

> Your command center. Open this when you launch Obsidian.

## Quick Actions

| Action | Link |
|--------|------|
| ✏️ New note in Inbox | `Cmd/Ctrl + N` (auto-lands in 00-Inbox) |
| 📅 Open today's daily note | `Cmd/Ctrl + P` → "Open today's daily note" |
| 🔍 Search vault | `Cmd/Ctrl + Shift + F` |
| 📊 Graph view | `Cmd/Ctrl + G` |

## Dashboards

| | |
|---|---|
| [[My Day]] | [[My Week]] |
| [[My Month]] | [[My Year]] |
| [[View - Tasks]] | [[View - Projects]] |
| [[View - Notes]] | [[View - Tags]] |
| [[GTD - Process]] | [[Kanban - Projects]] |

---

## 📬 Inbox (Unprocessed)

```dataview
TABLE WITHOUT ID
  file.link AS "Note",
  file.cday AS "Captured"
FROM "00-Inbox"
WHERE file.name != ".gitkeep" AND file.name != "Welcome to Your Vault"
SORT file.cday DESC
```

## 🔴 Overdue
*Tasks past their due date. Deal with these first.*

```dataview
TASK
WHERE !completed
  AND due
  AND due < date(today)
SORT due ASC
```

## ✅ Due Today
*Tasks due today, from anywhere in the vault.*

```dataview
TASK
WHERE !completed
  AND due = date(today)
SORT priority DESC
```

## 📓 From Today's Note
*Any open task written in today's daily note, due date or not.*

```dataview
TASK
FROM "05-Daily-Notes"
WHERE !completed AND file.day = date(today)
```

## 🚀 Active Projects

```dataview
TABLE WITHOUT ID
  link(file.path, regexreplace(file.folder, ".*/", "")) AS "Project",
  status AS "Status",
  target AS "Target Date"
FROM "01-Projects"
WHERE type = "project" AND status = "active"
SORT target ASC
```

## 📝 Recently Modified Notes

```dataview
TABLE WITHOUT ID
  file.link AS "Note",
  file.folder AS "Location",
  file.mday AS "Modified"
FROM ""
WHERE file.name != ".gitkeep"
  AND !contains(file.folder, "98-Templates")
  AND !contains(file.folder, "11-Dashboards")
  AND !contains(file.folder, ".obsidian")
SORT file.mday DESC
LIMIT 10
```
