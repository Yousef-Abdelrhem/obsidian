---
tags: [nodejs, package-managers, yarn]
status: in-progress
review_box: 1
review_due: 2026-07-22
last_reviewed: 2026-07-21
---
# yarn

## In my own words

yarn was created by Facebook in 2016 to fix npm's problems. It's faster than npm because it installs packages in parallel instead of one-by-one. It also has offline mode (can install without internet after first time) and better security checks.

However, yarn still duplicates packages like npm does, so pnpm has now surpassed it as the better alternative.

## How it connects
- [[Package Managers - npm vs yarn vs pnpm]]
- [[Lockfiles and Dependencies]]
- [[npm]]

## Pros
- Faster than npm (parallel installs)
- Better security (checks packages)
- Offline mode (cache packages locally)
- Smaller, more readable lockfile (yarn.lock)
- Better error messages than npm

## Cons
- Still creates duplicate dependencies (like npm)
- Slower than pnpm
- Less adoption now (declining use)
- Requires separate installation (not built-in)

## Common commands
```bash
yarn install              # Install all dependencies
yarn add lodash          # Add a specific package
yarn upgrade             # Update dependencies
yarn dev                 # Run a script
```

## When to use
- Legacy projects already using yarn
- Team prefers yarn's error messages
- Need offline mode
- Generally: **Don't choose yarn for new projects—use pnpm instead**

## Gotchas
- Switching from npm to yarn requires deleting `node_modules/` and `package-lock.json`, then running `yarn install`
- yarn.lock is incompatible with npm (and vice versa)
