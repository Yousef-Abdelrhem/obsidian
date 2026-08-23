---
tags: [os-fundamentals, docker]
linear: YOU-148
status: in-progress
review_box: 1
review_due: 2026-08-13
last_reviewed: 2026-08-12
---
# Containers vs Virtual Machines

## In my own words
The container is a process that is sharing our current machine's kernel. On the other hand, the virtual machine boots another full kernel and OS, not sharing the same kernel we use. Why this matters: the container sharing our kernel runs the process in milliseconds — a lot faster and lighter — than running a VM, which has to boot another kernel and OS. A container is like renting an apartment in a building and sharing the same resources the building is using, but the VM is like building a house next to the building that has its own structure, plumbing and electricity.

## How it connects
- [[Kernel]] — the one shared resource containers use directly and VMs duplicate
- [[Namespaces and cgroups]] — how a container fakes isolation despite sharing the kernel
- [[Docker Image vs Dockerfile vs Container]] — a container is the running instance; this note covers what makes it fast/light vs a VM

## Where it's used
Interview framing: "what is a container" / "container vs VM" — one of the most common Docker screening questions (KodeKloud "What Is A Container?" lesson, Docker Training Course for the Absolute Beginner). Also covers the container runtime history: LXC → libcontainer (2014, Docker v0.9.0) → runc (OCI standard) → containerd, with Docker itself as the friendly layer on top — `runc` is the actual low-level piece that creates/runs a container today.

## Gotchas
Interview-answer shape that works well: lead technical ("container shares the host kernel, VM virtualizes hardware and runs its own guest OS/kernel"), then explain *why it matters* (no second OS to boot → milliseconds startup, far less memory/disk), and only use the apartment/house analogy as an optional bridge — never as a replacement for the technical answer, since a pure-analogy answer can read as "doesn't know the real mechanism."
