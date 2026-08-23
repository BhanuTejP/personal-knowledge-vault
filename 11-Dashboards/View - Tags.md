---
tags:
  - type/dashboard
---

# 🏷️ Tags Index

> Browse your vault by tag. Also use Obsidian's native tag pane (`Cmd/Ctrl + P` → "Tags: Show tag pane").

## Status Tags

### Active
```dataview
LIST
FROM #status/active
SORT file.name ASC
```

### Paused
```dataview
LIST
FROM #status/paused
SORT file.name ASC
```

### Someday / Maybe
```dataview
LIST
FROM #someday
SORT file.name ASC
```

## Topic Tags

### Engineering
```dataview
LIST
FROM #engineering
SORT file.name ASC
```

### AI
```dataview
LIST
FROM #ai
SORT file.name ASC
```

### Angular
```dataview
LIST
FROM #angular
SORT file.name ASC
```

### Python
```dataview
LIST
FROM #python
SORT file.name ASC
```

### Django
```dataview
LIST
FROM #django
SORT file.name ASC
```

### Finance
```dataview
LIST
FROM #finance
SORT file.name ASC
```

### Writing
```dataview
LIST
FROM #writing
SORT file.name ASC
```

### Career
```dataview
LIST
FROM #career
SORT file.name ASC
```

## GTD Context Tags

### 💻 Computer
```dataview
TASK WHERE !completed AND contains(tags, "context/computer")
```

### 📱 Phone
```dataview
TASK WHERE !completed AND contains(tags, "context/phone")
```

### 🏢 Office
```dataview
TASK WHERE !completed AND contains(tags, "context/office")
```
