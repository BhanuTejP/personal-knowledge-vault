---
date: "2026-08-10"
type: project
status: active
area: Career
start: "2026-08-10"
target: "2026-09-15"
tags:
  - type/project
  - status/active
  - demo
---

# Project: Client Portal Redesign

## Outcome
Ship a redesigned client portal with the new Angular 19 signals-based dashboard and updated DRF endpoints, replacing the legacy jQuery admin panel.

## Why
Current portal has a 40% support-ticket rate tied to confusing navigation. Redesign targets a measurable drop in tickets and faster load times.

## Key Results / Deliverables
- [x] Finalize component library and design tokens
- [x] Migrate auth flow to signals-based state
- [ ] Rebuild dashboard with new API endpoints
- [ ] QA pass across all client tiers
- [ ] Staged rollout to 10% of clients

## Timeline
| Milestone | Target Date | Status |
|-----------|------------|--------|
| Design tokens locked | 2026-08-15 | ✅ Done |
| Auth migration | 2026-08-20 | ✅ Done |
| Dashboard rebuild | 2026-09-05 | 🔲 In progress |
| Staged rollout | 2026-09-15 | 🔲 Not started |

## Next Actions
- [ ] Rebuild client dashboard grid component #context/computer 📅 2026-08-25 ⏫
- [ ] Review DRF serializer performance on /clients endpoint #context/computer 📅 2026-08-27

## Tasks
- [ ] Write migration guide for support team #context/computer 📅 2026-08-28
- [x] Migrate auth flow to signals-based state
- [ ] Schedule QA handoff meeting #context/computer

## Decisions & Notes
Went with Angular signals over NgRx for this feature — team is small and the added ceremony of a full state library wasn't paying for itself on a portal this size. Revisit if the app grows past ~15 feature modules.

## Related
- **Area**: [[Career]]
- **People**: [[Jordan Lee]]
- **Resources**: [[MOC - Angular]]

## Log
### 2026-08-20
- Auth migration complete, all client sessions verified on staging

### 2026-08-15
- Design tokens locked with design team sign-off

### 2026-08-10
- Project created, kickoff meeting held
