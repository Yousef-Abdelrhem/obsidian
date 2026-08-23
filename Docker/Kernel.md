---
tags: [os-fundamentals, docker]
linear: YOU-148
status: in-progress
review_box: 1
review_due: 2026-08-13
last_reviewed: 2026-08-12
---
# Kernel

## In my own words
The kernel is the core part of the operating system that actually talks to the hardware (CPU, memory, disk) and manages who gets access to what. There's only one kernel running on a machine at a time, and every program ultimately relies on it to do things like read a file or use memory.

## How it connects
- [[Containers vs Virtual Machines]] — containers share the host's one kernel; VMs boot their own separate kernel
- [[Namespaces and cgroups]] — the kernel features that make a shared kernel still feel isolated per-container

## Where it's used
Referenced in KodeKloud's "What Is A Container?" lesson (Docker Training Course for the Absolute Beginner) to explain why containers are lighter than VMs.

## Gotchas
Easy to think a container has "its own separate files/kernel" — it doesn't. The kernel is always the one shared thing; what's separate is only what each container is *allowed to see* (see [[Namespaces and cgroups]]).
