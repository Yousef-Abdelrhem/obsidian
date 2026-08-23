---
tags: [typeorm, typeorm-mastery]
linear: TYP-11
status: done
review_box: 1
review_due: 2026-07-22
last_reviewed: 2026-07-21
---
# Explicit Junction Entities

## In my own words
We need a junction table in relationships that use `@ManyToMany` because without it, we'd create a lot of messy fields or empty columns that don't get used. For example, with User and Tag entities, each user has many tags and each tag belongs to many users. Without a junction table, we'd have nowhere to store those pairs. So we create a junction table that stores the `tag_id` and `user_id` together — one row per pair.

## How it connects
- [[7 - Relations OneToOne and ManyToMany]]

## Where SMAW-SAAS uses it
SMAW-SAAS avoids `@ManyToMany` project-wide, even where it would technically fit (e.g. `User`/`Role`). Instead it hand-writes a junction entity like `UserRole` with its own primary key, `createdAt`, and room for extra columns — things a `@ManyToMany` auto-generated junction table can't hold.

## Gotchas
The tradeoff: more boilerplate (a whole entity + repository) for full control over the join table (extra columns, direct querying, timestamps).
