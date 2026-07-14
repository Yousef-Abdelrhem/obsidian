---
tags: [typeorm, typeorm-mastery]
linear: TYP-11
status: in-progress
review_box: 1
review_due: 2026-07-14
last_reviewed: 2026-07-13
---
# JoinColumn Ownership

## In my own words
> [!PLACEHOLDER] Not filled in yet — needs Yousef's own explanation before this is real.

## How it connects
- [[7 - Relations OneToOne and ManyToMany]]

## Where it's used
`@JoinColumn()` marks the owning side of a `@OneToOne` relation — that's where the foreign key column physically lives. Put it on the wrong entity and TypeORM either errors or creates the FK on the wrong table. For `@ManyToMany`, the equivalent is `@JoinTable()` on the owning side.

## Gotchas
Putting `@JoinColumn()` on both sides creates two FK columns. Rule of thumb: it belongs on whichever entity is semantically the "child" (e.g. `Profile` belongs to `User`).
