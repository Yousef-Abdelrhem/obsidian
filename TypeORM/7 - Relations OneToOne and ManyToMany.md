---
tags: [typeorm, typeorm-mastery]
linear: TYP-11
status: in-progress
review_box: 1
review_due: 2026-07-14
last_reviewed: 2026-07-13
---
# 7. Relations: @OneToOne & @ManyToMany

[Linear issue](https://linear.app/typeorm/issue/TYP-11/7-relations-onetoone-and-manytomany)

## In my own words
> [!PLACEHOLDER] Not filled in yet — this section must come from Yousef's own explanation, elicited before writing, never from Claude's paraphrase. The skill asked the recall question in chat and got "continue" instead of an answer, so this is scaffold-only. Come back and dictate the real explanation, then replace this block.

## How it connects
- [[JoinColumn Ownership]]
- [[Explicit Junction Entities]]

## Where SMAW-SAAS uses it
`libs/typeorm-user/src/lib/entities/tenant-user.entity.ts` — `TenantUser` is the owning side of a `@OneToOne` with `User` (holds `@JoinColumn()`). SMAW-SAAS avoids `@ManyToMany` project-wide — e.g. `User`/`Role` uses an explicit `UserRole` junction entity instead.

## Gotchas
`@JoinColumn()` on the wrong side puts the FK column on the wrong table. Rule: it goes on the semantic "child" entity — the one that "belongs to" the other (e.g. `Profile` belongs to `User`, so `Profile` gets `@JoinColumn()`).
