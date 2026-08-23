---
tags: [nodejs, package-managers, dependencies]
status: in-progress
review_box: 1
review_due: 2026-07-22
last_reviewed: 2026-07-21
---
# Lockfiles and Dependencies

## In my own words

When you specify a dependency in `package.json`, you usually use a version range like `^4.17.21` (meaning "any 4.x version"). This is flexible but risky—two developers might install different versions.

A lockfile **locks the exact versions** so everyone installs the same thing. This prevents "it works on my machine but not in production" bugs.

Each package manager has its own lockfile format:
- npm uses `package-lock.json`
- yarn uses `yarn.lock`
- pnpm uses `pnpm-lock.yaml`

## How it connects
- [[npm]]
- [[yarn]]
- [[pnpm]]
- [[Package Managers - npm vs yarn vs pnpm]]

## package.json vs Lockfile

**package.json** — What YOU specify (flexible):
```json
{
  "dependencies": {
    "lodash": "^4.17.21"  // "any 4.x version"
  }
}
```

**Lockfile** — What ACTUALLY gets installed (exact):
```
lodash@4.17.21  (locked to this exact version)
```

## Why lockfiles matter
1. **Reproducibility** — Same code everywhere (dev, staging, production)
2. **Consistency** — Whole team installs same versions
3. **Bug prevention** — A new version of a package can't break your code unexpectedly
4. **CI/CD** — Production deploys use exact versions, not ranges

## Common gotcha: npm install vs npm ci

```bash
npm install    # May update versions (respects ^4.17.21 range)
npm ci         # Installs exact lockfile versions (recommended for CI/CD)
```

In production (CI/CD), ALWAYS use `npm ci` or equivalent (`pnpm install --frozen-lockfile`), not `npm install`.

## Lockfile strategies
- **Commit lockfiles to git** ✅ (so everyone has same versions)
- **Don't commit node_modules/** ✅ (lockfile is enough)
- **Regenerate lockfiles after major updates** (test everything after)
