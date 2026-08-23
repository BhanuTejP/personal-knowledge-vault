---
tags:
  - type/dashboard
---

# 🎯 My Year

> Yearly goals, progress, and big picture.

## Yearly Goals
> Set these at the start of the year. Track progress in monthly reviews.

```dataview
TABLE WITHOUT ID
  file.link AS "Goal",
  status AS "Status",
  timeframe AS "Timeframe",
  area AS "Area"
FROM "02-Areas/Goals"
WHERE type = "goal"
SORT status ASC
```

## Projects Completed This Year

```dataview
TABLE WITHOUT ID
  link(file.path, regexreplace(file.folder, ".*/", "")) AS "Project",
  target AS "Completed"
FROM "04-Archives/Projects"
WHERE type = "project"
  AND file.cday.year = date(today).year
SORT file.cday DESC
```

## Books Read This Year

```dataview
TABLE WITHOUT ID
  file.link AS "Book",
  author AS "Author",
  rating AS "Rating"
FROM "10-Books"
WHERE status = "finished"
  AND file.cday.year = date(today).year
SORT file.cday DESC
```

## Articles Published This Year

```dataview
TABLE WITHOUT ID
  file.link AS "Article",
  status AS "Status",
  platform AS "Platform"
FROM ""
WHERE contains(tags, "type/article")
  AND file.cday.year = date(today).year
SORT file.cday DESC
```

## Yearly Review

> Go to `08-Yearly-Notes/` for your yearly reviews.
