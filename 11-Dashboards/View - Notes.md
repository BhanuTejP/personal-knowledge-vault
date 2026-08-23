---
tags:
  - type/dashboard
---

# 📝 All Notes

> Browse recently created and modified notes.

## Recently Created

```dataview
TABLE WITHOUT ID
  file.link AS "Note",
  file.folder AS "Location",
  file.cday AS "Created"
FROM ""
WHERE file.name != ".gitkeep"
  AND !contains(file.folder, "98-Templates")
  AND !contains(file.folder, "11-Dashboards")
  AND !contains(file.folder, ".obsidian")
SORT file.cday DESC
LIMIT 20
```

## Recently Modified

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
  AND file.mday != file.cday
SORT file.mday DESC
LIMIT 20
```

## By Type

### 📚 Books
```dataview
TABLE WITHOUT ID file.link AS "Book", author AS "Author", rating AS "Rating", status AS "Status"
FROM "10-Books"
SORT file.cday DESC
```

### 👤 People
```dataview
TABLE WITHOUT ID file.link AS "Person", company AS "Company", role AS "Role", relationship AS "Relationship"
FROM "09-People"
SORT file.name ASC
```

### 🎓 Learning Notes
```dataview
TABLE WITHOUT ID file.link AS "Note", topic AS "Topic", date AS "Date"
FROM ""
WHERE contains(tags, "type/learning")
SORT file.cday DESC
```

### 🏛️ Architecture Decisions
```dataview
TABLE WITHOUT ID file.link AS "ADR", status AS "Status", date AS "Date"
FROM ""
WHERE contains(tags, "type/adr")
SORT file.cday DESC
```

### 🗺️ Maps of Content
```dataview
LIST
FROM "03-Resources/MOCs"
SORT file.name ASC
```
