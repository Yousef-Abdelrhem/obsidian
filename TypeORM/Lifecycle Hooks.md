---
tags: [typeorm, typeorm-mastery]
linear: TYP-12
status: in-progress
review_box: 1
review_due: 2026-07-22
last_reviewed: 2026-07-21
---
# Lifecycle Hooks

## In my own words

Lifecycle hooks are decorators that run code at specific moments in an entity's life — before insert, before update, after load, etc. They only run when you use `save()` to persist the entity. If you use `update()` with raw SQL, lifecycle hooks don't run because there's no entity in memory.

## How it connects
- [[8 - Date Columns and Base Entity Inheritance]]
- [[Save vs Update Gotcha]]

## Where it's used

Common hooks:
- `@BeforeInsert()` — runs before a new row is inserted (used to generate IDs or hash passwords)
- `@BeforeUpdate()` — runs before an update
- `@AfterLoad()` — runs after TypeORM fetches a row from the database

## Examples

**Generate UUID before insert:**
```typescript
@BeforeInsert()
generateId() {
  this.id = randomUUID();
}
```

**Hash password before insert:**
```typescript
@BeforeInsert()
async hashPassword() {
  this.password = await bcrypt.hash(this.password, 10);
}
```

## Gotchas

Lifecycle hooks only run during the entity lifecycle when using `save()`. Direct SQL via `update()` bypasses them completely.
