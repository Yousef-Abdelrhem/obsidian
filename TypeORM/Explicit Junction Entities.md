---
tags: [typeorm, typeorm-mastery]
linear: TYP-11
status: in-progress
review_box: 1
review_due: 2026-07-14
last_reviewed: 2026-07-13
---
# Explicit Junction Entities

## In my own words
> [!PLACEHOLDER] Not filled in yet — needs Yousef's own explanation before this is real.

## How it connects
- [[7 - Relations OneToOne and ManyToMany]]

## Where SMAW-SAAS uses it
SMAW-SAAS avoids `@ManyToMany` project-wide, even where it would technically fit (e.g. `User`/`Role`). Instead it hand-writes a junction entity like `UserRole` with its own primary key, `createdAt`, and room for extra columns — things a `@ManyToMany` auto-generated junction table can't hold.

## Gotchas
The tradeoff: more boilerplate (a whole entity + repository) for full control over the join table (extra columns, direct querying, timestamps).
