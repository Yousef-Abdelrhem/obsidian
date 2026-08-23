---
tags: [typeorm, typeorm-mastery]
linear: TYP-12
status: in-progress
review_box: 1
review_due: 2026-07-22
last_reviewed: 2026-07-21
---
# Base Entity Pattern

## In my own words

Instead of repeating `id`, `createdAt`, `updatedAt`, `createdBy` in every entity, create an abstract base class with these common fields. Every concrete entity extends it and automatically inherits all those columns without duplicating code.

## How it connects
- [[8 - Date Columns and Base Entity Inheritance]]

## Where it's used

SMAW-SAAS uses `BaseEntity` (or `BaseTenantEntity`) as the parent for ALL entities. This ensures consistency: every table has the same audit columns (`id`, `createdAt`, `updatedAt`, `createdBy`, `updatedBy`).

```typescript
// base.entity.ts
export abstract class BaseEntity {
  @PrimaryColumn()
  id: string;

  @CreateDateColumn()
  createdAt: Date;

  @UpdateDateColumn()
  updatedAt: Date;

  @Column({ nullable: true })
  createdBy: string | null;

  @BeforeInsert()
  generateId() {
    this.id = randomUUID();
  }
}

// user.entity.ts
@Entity()
export class User extends BaseEntity {
  // id, createdAt, updatedAt, createdBy are inherited
  @Column()
  name: string;
}
```

## Gotchas

- `abstract class` means you can't do `new BaseEntity()` — only extend it
- `@Entity()` must be on the concrete subclass (User, Post, etc.), NOT on the abstract base
- Without `@Entity()` on the subclass, TypeORM ignores it
