---
date: "2026-08-21"
type: project
status: active
area: Side Projects
start: "2026-08-21"
target: "2026-10-01"
tags:
  - type/project
  - status/active
  - demo
---

# Project: Obsidian Plugin — Sync Status Bar

## Outcome
Small open-source Obsidian plugin that shows Git sync status (ahead/behind/clean) in the status bar for vaults backed by Git.

## Why
Keep losing track of whether I've pushed today. Wanted a glanceable indicator instead of opening a terminal.

## Key Results / Deliverables
- [ ] Detect Git status via local .git directory
- [ ] Render status bar icon with ahead/behind counts
- [ ] Publish to community plugin list

## Timeline
| Milestone | Target Date | Status |
|-----------|------------|--------|
| Working prototype | 2026-09-05 | 🔲 Not started |
| Public beta | 2026-09-20 | 🔲 Not started |
| Community plugin submission | 2026-10-01 | 🔲 Not started |

## Next Actions
- [ ] Scaffold plugin using Obsidian sample plugin template #context/computer 📅 2026-08-24

## Tasks
- [ ] Research how Obsidian Git plugin reads status internally #context/computer #someday

## Decisions & Notes
Early days — just scaffolding this week. Might fold into Obsidian Git itself as a PR instead of a standalone plugin if the maintainer is open to it.

## Related
- **Area**: [[Side-Projects]]
- **Resources**: [[MOC - Angular]]

## Log
### 2026-08-21
- Project created, evaluating standalone plugin vs upstream PR
