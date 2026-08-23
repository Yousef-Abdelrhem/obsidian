---
tags: [typeorm, typeorm-mastery]
linear: TYP-12
status: in-progress
review_box: 1
review_due: 2026-07-22
last_reviewed: 2026-07-21
---
# 8. Date Columns & Base Entity Inheritance

[Linear issue](https://linear.app/typeorm/issue/TYP-12/8-date-columns-and-base-entity-inheritance)

## In my own words

**Magic date columns:** `@CreateDateColumn()` automatically sets a timestamp when a row is inserted. `@UpdateDateColumn()` automatically updates the timestamp whenever the row is modified via `save()`.

**Lifecycle hooks:** Decorators like `@BeforeInsert()` let you run code before TypeORM executes an INSERT or UPDATE. They only run when you use `save()` — not when you use `update()`.

**Base entity inheritance:** Instead of repeating `id`, `createdAt`, `updatedAt`, `createdBy` in every entity, create an abstract `BaseEntity` class with these fields. Every concrete entity extends it and inherits all these columns for free.

**save() vs update():** `save()` loads the entity, runs all lifecycle hooks and decorators (@UpdateDateColumn, @BeforeUpdate, etc.), then saves. `update()` uses raw SQL and completely bypasses lifecycle hooks — that's why @UpdateDateColumn doesn't work with it.

## How it connects
- [[Lifecycle Hooks]]
- [[Base Entity Pattern]]
- [[Save vs Update Gotcha]]

## Where SMAW-SAAS uses it
`libs/typeorm-forms/src/lib/entities/base-tenant.entity.ts` — the abstract base class that all entities extend. It has `id` (UUID v7 via @BeforeInsert), `createdAt`, `updatedAt`, `createdBy`, `updatedBy`, `tenantId`, and `@DeleteDateColumn()` for soft deletes.

## Gotchas
1. `@UpdateDateColumn` only works with `save()`, not `update()` — this is a common bug
2. `abstract class` means you can't instantiate it directly — only extend it
3. `@Entity()` must be on the concrete subclass, not the abstract base
