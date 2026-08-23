---
tags: [typeorm, typeorm-mastery]
linear: TYP-11
status: done
review_box: 1
review_due: 2026-07-22
last_reviewed: 2026-07-21
---
# 7. Relations: @OneToOne & @ManyToMany

[Linear issue](https://linear.app/typeorm/issue/TYP-11/7-relations-onetoone-and-manytomany)

## In my own words

**@OneToOne:** Profile holds the foreign key to User because Profile "belongs to" User. The `@JoinColumn()` decorator marks the owning side — the side where the FK physically lives. TypeORM uses this to load the relation in both directions, but the FK is what enforces database consistency.

**@ManyToMany:** Without a junction table, you'd have empty columns or messy fields. A junction table stores pairs of IDs (userId, tagId) — one row per relationship. SMAW-SAAS uses explicit junction entities instead of the `@ManyToMany` decorator because explicit entities let you add timestamps, extra columns, and control indexes.

## How it connects
- [[JoinColumn Ownership]]
- [[Explicit Junction Entities]]

## Where SMAW-SAAS uses it
`libs/typeorm-user/src/lib/entities/tenant-user.entity.ts` — `TenantUser` is the owning side of a `@OneToOne` with `User` (holds `@JoinColumn()`). SMAW-SAAS avoids `@ManyToMany` project-wide — e.g. `User`/`Role` uses an explicit `UserRole` junction entity instead.

## Gotchas
`@JoinColumn()` on the wrong side puts the FK column on the wrong table. Rule: it goes on the semantic "child" entity — the one that "belongs to" the other (e.g. `Profile` belongs to `User`, so `Profile` gets `@JoinColumn()`).
