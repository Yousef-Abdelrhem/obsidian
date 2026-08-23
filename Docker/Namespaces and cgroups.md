---
tags: [os-fundamentals, docker]
linear: YOU-148
status: in-progress
review_box: 1
review_due: 2026-08-13
last_reviewed: 2026-08-12
---
# Namespaces and cgroups

## In my own words
The container has its own process and its own network — that's what namespaces isolation means. Even though it's one shared kernel, namespaces don't show container A's processes to container B's process. And each one has cgroups which limits how much of the CPU the process is taking.

## How it connects
- [[Kernel]] — namespaces and cgroups are both kernel features enforced on top of the one shared kernel, nothing is physically separated
- [[Containers vs Virtual Machines]] — this is the actual mechanism behind "containers feel isolated despite sharing a kernel"

## Where it's used
Common interview follow-up to "what is a container": "how does it actually get isolated if it shares the kernel?" — the real answer is namespaces (isolation/visibility) + cgroups (resource limits), not "it has its own kernel."

## Gotchas
- **Namespaces = isolation (what you can see)**, **cgroups = limits (how much you can use)** — easy to blur the two together.
- Naming collision to watch for: "namespace" also means something completely different in OOP/C++ (a code-organization construct to prevent name conflicts — see [[OOP]]). Same word, unrelated concept — don't cross-wire them in an interview answer.
- Apartment analogy: namespaces = each apartment's own locked door/mailbox (can't see into the neighbor's unit); cgroups = the building's electrical panel capping how much power your unit can draw.
