---
tags:
  - type/dashboard
---

# 🚀 All Projects

> Every project across the vault.

## Active Projects

```dataview
TABLE WITHOUT ID
  link(file.path, regexreplace(file.folder, ".*/", "")) AS "Project",
  area AS "Area",
  start AS "Started",
  target AS "Target",
  status AS "Status"
FROM "01-Projects"
WHERE type = "project" AND status = "active"
SORT target ASC
```

## Paused Projects

```dataview
TABLE WITHOUT ID
  link(file.path, regexreplace(file.folder, ".*/", "")) AS "Project",
  area AS "Area",
  status AS "Status"
FROM "01-Projects"
WHERE type = "project" AND status = "paused"
SORT file.name ASC
```

## Recently Archived

```dataview
TABLE WITHOUT ID
  link(file.path, regexreplace(file.folder, ".*/", "")) AS "Project",
  target AS "Completed"
FROM "04-Archives/Projects"
WHERE type = "project"
SORT file.mday DESC
LIMIT 10
```

## Projects by Area

### Career
```dataview
LIST link(file.path, regexreplace(file.folder, ".*/", ""))
FROM "01-Projects"
WHERE type = "project" AND area = "Career"
```

### Side Projects
```dataview
LIST link(file.path, regexreplace(file.folder, ".*/", ""))
FROM "01-Projects"
WHERE type = "project" AND area = "Side Projects"
```

### Writing
```dataview
LIST link(file.path, regexreplace(file.folder, ".*/", ""))
FROM "01-Projects"
WHERE type = "project" AND area = "Writing"
```

### Learning
```dataview
LIST link(file.path, regexreplace(file.folder, ".*/", ""))
FROM "01-Projects"
WHERE type = "project" AND area = "Learning"
```
