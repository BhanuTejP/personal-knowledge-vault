---
date: "2026-08-05"
title: "Designing Data-Intensive Applications"
author: "Martin Kleppmann"
category: "Engineering"
rating: 5/5
status: reading
tags:
  - type/book
  - demo
---

# Book: Designing Data-Intensive Applications

**Author**: Martin Kleppmann
**Category**: Engineering / Systems
**Started**: 2026-08-05
**Finished**: 

## Why I Read This
Kept hitting distributed-systems questions at work I couldn't reason about confidently — replication, consistency guarantees, partitioning trade-offs. This is the standard reference.

## Summary
A deep, practical look at the fundamentals behind modern data systems — storage engines, replication, partitioning, transactions, and consistency — without tying itself to any one specific database or framework.

## Key Takeaways
1. Multi-leader replication trades availability for the possibility of write conflicts — you can't get both for free
2. "Eventually consistent" hides a lot of important nuance about *how* eventual and under what failure conditions
3. Partitioning strategy should follow query patterns, not just data volume

## Favourite Quotes / Passages
> 

## Chapter Notes
### Chapter 5 — Replication
Multi-leader replication's conflict resolution problem maps almost exactly onto a sync-conflict issue we punted on in the client portal redesign. Worth revisiting that decision with this framing.

## How This Connects
Directly relevant to [[api-rate-limiter]] — the rate limiter's shared-state problem across multiple gateway instances is essentially a mini version of the replication consistency trade-offs in this book.

- [[MOC - System Design]]

## Would I Recommend?
Yes, especially for anyone doing backend/infra work who's absorbed patterns without the underlying theory.
