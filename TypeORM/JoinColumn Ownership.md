---
tags: [typeorm, typeorm-mastery]
linear: TYP-11
status: done
review_box: 1
review_due: 2026-07-22
last_reviewed: 2026-07-21
---
# JoinColumn Ownership

## In my own words
The entity that gets the foreign key is the one that "belongs to" the other — like Profile belongs to User. Profile gets `@JoinColumn()` so it can access the User data. But TypeORM also lets the User entity see the Profile through the relationship decorator, which is why you get bidirectional access. We use the FK because it enforces database rules — the FK ensures data consistency and prevents orphaned records.

## How it connects
- [[7 - Relations OneToOne and ManyToMany]]

## Where it's used
`@JoinColumn()` marks the owning side of a `@OneToOne` relation — that's where the foreign key column physically lives. Put it on the wrong entity and TypeORM either errors or creates the FK on the wrong table. For `@ManyToMany`, the equivalent is `@JoinTable()` on the owning side.

## Gotchas
Putting `@JoinColumn()` on both sides creates two FK columns. Rule of thumb: it belongs on whichever entity is semantically the "child" (e.g. `Profile` belongs to `User`).
