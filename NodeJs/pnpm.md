---
tags: [nodejs, package-managers, pnpm]
status: in-progress
review_box: 1
review_due: 2026-07-22
last_reviewed: 2026-07-21
---
# pnpm

## In my own words

pnpm is the modern package manager. It's the fastest and uses the least disk space because it stores each package only ONCE in a central store (`.pnpm/`), and all projects just point to it via symlinks (shortcuts). Instead of wasting 500MB with duplicates, pnpm uses 150MB.

pnpm also has strict dependency isolation—a package can't accidentally use another package's dependency. This prevents bugs that npm/yarn wouldn't catch.

## How it connects
- [[Package Managers - npm vs yarn vs pnpm]]
- [[Lockfiles and Dependencies]]
- [[npm]]
- [[yarn]]

## Pros
- **Fastest** package manager (parallel installs + better algorithms)
- **Smallest disk footprint** (50-70% smaller than npm/yarn via symlinks)
- **Strict dependency isolation** (prevents "phantom dependencies" bugs)
- Monorepo support built-in
- Backward compatible with npm
- Modern adoption (used by Vite, Turborepo, and many new projects)

## Cons
- Newer (less adoption in old projects)
- Some edge cases with tools that expect npm's `node_modules` structure
- Requires separate installation

## How it works (the magic)
```
npm/yarn structure:
node_modules/
├── lodash/  (full copy 1)
├── package-a/
│   └── node_modules/
│       └── lodash/  (full copy 2 — DUPLICATE!)
└── package-b/
    └── node_modules/
        └── lodash/  (full copy 3 — DUPLICATE!)

pnpm structure (with symlinks):
node_modules/
├── .pnpm/  (central store)
│   ├── lodash@4.17.21/  (ONE copy, stored once)
│   ├── package-a@1.0.0/
│   └── package-b@2.0.0/
├── lodash → .pnpm/lodash@4.17.21/  (symlink = shortcut)
├── package-a → .pnpm/package-a@1.0.0/
└── package-b → .pnpm/package-b@2.0.0/
```

Result: 50-70% smaller, much faster!

## Common commands
```bash
pnpm install              # Install all dependencies
pnpm add lodash          # Add a package
pnpm update              # Update dependencies
pnpm dev                 # Run a script
```

## When to use
- **NEW projects** (especially monorepos) — highly recommended
- You care about performance and disk space
- Modern teams (Vite, Next.js 15+, TypeScript projects)
- Monorepo setup (pnpm workspaces are superior)

## Interview angle
"pnpm uses symlinks to store each package only once in a central store, instead of duplicating like npm/yarn. This makes it 70% smaller and much faster—ideal for monorepos and modern projects."

## Gotchas
- Switching to pnpm requires `pnpm install` (regenerates lockfile as pnpm-lock.yaml)
- Some old tools don't work with symlinks (rare, but possible)
- Team needs to all use pnpm (can't mix with npm on same project)
