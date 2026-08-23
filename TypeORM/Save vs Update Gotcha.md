---
tags: [typeorm, typeorm-mastery]
linear: TYP-12
status: in-progress
review_box: 1
review_due: 2026-07-22
last_reviewed: 2026-07-21
---
# Save vs Update Gotcha

## In my own words

`save()` loads the entity, modifies it, runs all lifecycle hooks and decorators like `@UpdateDateColumn` and `@BeforeUpdate`, then saves it. `update()` uses raw SQL and completely bypasses lifecycle hooks — that's why `@UpdateDateColumn` doesn't work with it.

## How it connects
- [[8 - Date Columns and Base Entity Inheritance]]
- [[Lifecycle Hooks]]

## The Problem

```typescript
// ❌ WRONG: updatedAt does NOT change
await userRepo.update(userId, { name: 'New Name' });

// ✅ RIGHT: updatedAt DOES change
const user = await userRepo.findOne(userId);
user.name = 'New Name';
await userRepo.save(user);
```

## Why?

**save():** Load entity → modify in memory → run lifecycle hooks → save
- Steps: SELECT (load), run decorators, UPDATE (with new updatedAt)
- Slower (2 queries) but full lifecycle

**update():** Execute raw SQL UPDATE directly
- Steps: UPDATE (no entity in memory, no hooks)
- Faster (1 query) but NO lifecycle hooks, NO @UpdateDateColumn

## When to use each

- Use `save()` for normal updates (when you need timestamps and decorators to run)
- Use `update()` for bulk updates where you don't need lifecycle hooks (performance optimization)

## Gotchas

This is a **common source of bugs**: developers expect `updatedAt` to update after `repository.update()`, but it doesn't. Always use `save()` unless you have a specific performance reason to use `update()`.
