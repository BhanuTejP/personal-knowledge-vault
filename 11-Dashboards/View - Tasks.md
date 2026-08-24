---
tags:
  - type/dashboard
---

# ✅ All Tasks

> Global view of every task across the vault.

## Overdue

```dataview
TASK
WHERE !completed
  AND due < date(today)
  AND due != null
SORT due ASC
```

## Due Today

```dataview
TASK
WHERE !completed
  AND due = date(today)
SORT priority DESC
```

## Due This Week

```dataview
TASK
WHERE !completed
  AND due > date(today)
  AND due <= date(today) + dur("7 days")
SORT due ASC
```

## In Progress

```dataview
TASK
WHERE status = "/"
  AND !completed
SORT file.name ASC
```

## Waiting For

```dataview
TASK
WHERE status = "w"
  AND !completed
SORT file.name ASC
```

## High Priority (No Due Date)

```dataview
TASK
WHERE !completed
  AND due = null
  AND contains(text, "⏫")
SORT file.name ASC
```

## Someday / Maybe

```dataview
TASK
WHERE !completed
  AND contains(tags, "#someday")
SORT file.name ASC
```

## By Context

### 💻 Computer
```dataview
TASK
WHERE !completed AND contains(tags, "#context/computer")
SORT due ASC
```

### 📱 Phone
```dataview
TASK
WHERE !completed AND contains(tags, "#context/phone")
SORT due ASC
```

### 🏢 Office
```dataview
TASK
WHERE !completed AND contains(tags, "#context/office")
SORT due ASC
```

### 🏠 Home
```dataview
TASK
WHERE !completed AND contains(tags, "#context/home")
SORT due ASC
```

### 🛒 Errand
```dataview
TASK
WHERE !completed AND contains(tags, "#context/errand")
SORT due ASC
```

## Recently Completed

```dataview
TASK
WHERE completed
  AND completion >= date(today) - dur("7 days")
SORT completion DESC
```
