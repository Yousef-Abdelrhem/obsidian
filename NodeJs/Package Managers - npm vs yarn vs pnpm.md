---
tags: [nodejs, package-managers, interview-prep]
status: in-progress
review_box: 1
review_due: 2026-07-22
last_reviewed: 2026-07-21
---
# Package Managers — npm vs yarn vs pnpm

## In my own words

A package manager is a tool that downloads and installs code libraries (dependencies) from a registry. The main difference between npm, yarn, and pnpm is **how they store packages** and **performance**:

- **npm** is the default, built into Node.js, but wastes disk space by duplicating packages
- **yarn** was faster and added offline support, but still duplicates packages
- **pnpm** is the modern choice—it uses symlinks to store each package only once, making it 70% smaller and much faster

The core insight: npm and yarn duplicate packages (if lodash is needed by 10 different packages, you get 10 copies). pnpm deduplicates via symlinks (all 10 point to one lodash in a central store).

## How it connects
- [[npm]]
- [[yarn]]
- [[pnpm]]
- [[Lockfiles and Dependencies]]

## Where it's used

Every Node.js project uses one of these three. Interview questions often ask to explain the differences and when to use each.

## Gotchas

1. Many projects still use npm (it's the default) even though pnpm is objectively better
2. Some older tools don't work well with pnpm's symlink approach
3. Switching package managers on an existing project requires regenerating lockfiles
4. The "best" choice depends on team standards, not just technical merit
