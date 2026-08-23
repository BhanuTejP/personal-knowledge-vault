---
date: "2026-07-28"
type: project
status: active
area: Career
start: "2026-07-28"
target: "2026-08-20"
tags:
  - type/project
  - status/active
  - demo
---

# Project: API Rate Limiter

## Outcome
Add a token-bucket rate limiter middleware to the FastAPI gateway so no single client can degrade service for others.

## Why
Third-party integration partner hit our API hard enough last month to cause a brief outage for everyone else. This closes that gap.

## Key Results / Deliverables
- [x] Research token-bucket vs sliding-window approaches
- [x] Prototype middleware in FastAPI
- [ ] Load test against production-like traffic
- [ ] Deploy to staging
- [ ] Deploy to production

## Timeline
| Milestone | Target Date | Status |
|-----------|------------|--------|
| Prototype complete | 2026-08-05 | ✅ Done |
| Load testing | 2026-08-20 | 🔴 Overdue |
| Production deploy | 2026-09-01 | 🔲 Not started |

## Next Actions
- [ ] Set up k6 load test scenarios against staging #context/computer 📅 2026-08-19 ⏫
- [ ] Get sign-off from infra team on rollout plan #context/office 📅 2026-08-21

## Tasks
- [ ] Document rate limit headers for API consumers #context/computer 📅 2026-08-26
- [w] **@Jordan Lee** — waiting on infra capacity numbers before load testing

## Decisions & Notes
Load testing has slipped twice now — infra team's staging environment doesn't match production traffic patterns closely enough. Need to either get real anonymized traffic replay or accept some risk on the load test results.

## Related
- **Area**: [[Career]]
- **People**: [[Jordan Lee]]
- **Resources**: [[MOC - Python]]

## Log
### 2026-08-18
- Blocked again on staging environment — escalated to infra team

### 2026-08-05
- Prototype passes initial correctness tests

### 2026-07-28
- Project kicked off after the partner-traffic incident
