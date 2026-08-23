---
date: "2026-08-22"
tags:
  - type/area
---

# Goals

> Master list of goals across all areas.

## Active Goals

```dataview
TABLE WITHOUT ID
  file.link AS "Goal",
  status AS "Status",
  timeframe AS "Timeframe",
  area AS "Area"
FROM "02-Areas/Goals"
WHERE type = "goal" AND status = "active"
SORT timeframe ASC
```

## Completed Goals

```dataview
TABLE WITHOUT ID
  file.link AS "Goal",
  area AS "Area"
FROM "02-Areas/Goals"
WHERE type = "goal" AND status = "done"
SORT file.mday DESC
```
