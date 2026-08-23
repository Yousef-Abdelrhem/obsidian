---
tags: [nodejs, package-managers, npm]
status: in-progress
review_box: 1
review_due: 2026-07-22
last_reviewed: 2026-07-21
---
# npm (Node Package Manager)

## In my own words

npm is the default package manager for Node.js. It comes automatically when you install Node.js, so most developers use it. It's simple to learn and works for any project, but it wastes disk space because it duplicates packages.

When you run `npm install`, it downloads packages from the npm registry and stores them in `node_modules/`. If many packages need lodash, npm creates a separate copy of lodash for each one.

## How it connects
- [[Package Managers - npm vs yarn vs pnpm]]
- [[Lockfiles and Dependencies]]

## Pros
- Built into Node.js (no separate install)
- Huge ecosystem (millions of packages)
- Simple and straightforward
- Standard across most projects
- Best for beginners

## Cons
- Slower than yarn and pnpm
- Creates duplicate dependencies (wastes ~500MB+ for medium projects)
- Flat node_modules can have conflicts
- Generates larger lockfile

## Common commands
```bash
npm install                 # Install all dependencies
npm install lodash         # Install a specific package
npm update                 # Update to latest versions
npm run dev               # Run a script from package.json
```

## When to use
- Team requires npm (most companies)
- Beginner learning projects
- Default choice if no preference

## Gotchas
- `npm update` can change versions unexpectedly (use npm ci in production)
- Phantom dependencies (a package can access another package's dependency indirectly)
