---
kanban-plugin: basic
tags:
  - type/dashboard
---

# 📋 Kanban — Projects

> Install the **Kanban** community plugin to use this as a drag-and-drop board.
> Open this note → `Cmd/Ctrl + P` → "Kanban: Board view" to switch to board mode.

## Backlog

- [ ] [[01-Projects/obsidian-plugin-sync/Overview|obsidian-plugin-sync]]

## In Progress

- [ ] [[01-Projects/client-portal-redesign/Overview|client-portal-redesign]]
- [ ] [[01-Projects/api-rate-limiter/Overview|api-rate-limiter]]

## Waiting / Blocked

- [ ] [[01-Projects/api-rate-limiter/Overview|api-rate-limiter]] — blocked on infra staging environment

## Done

- [ ] Design tokens locked (client-portal-redesign milestone)
- [ ] Auth migration shipped (client-portal-redesign milestone)

---

> **How to use**: Each card is a `- [ ]` checkbox linking to a project's `Overview.md`.
> Since every project's main file is literally named `Overview.md`, a plain link like `[[auth-redesign]]` won't resolve — use the full path with a pipe alias so it both opens correctly and displays the project name:
> `- [ ] [[01-Projects/auth-redesign/Overview|auth-redesign]]`
> Tip: type `[[`, then start typing the project folder name — Obsidian's autocomplete will find the real `Overview.md` file for you. Just add `|ProjectName` after picking it so the card shows a clean label instead of "Overview."
> Drag cards between columns in Kanban view.
