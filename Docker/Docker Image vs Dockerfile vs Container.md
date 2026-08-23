---
tags: [docker]
linear: YOU-148
status: in-progress
review_box: 1
review_due: 2026-08-13
last_reviewed: 2026-08-12
---
# Docker Image vs Dockerfile vs Container

## In my own words
The Dockerfile is a text file that shows us what type of OS to use, the dependencies to install, and when the container runs, we define commands to run. The image is like files on your disk waiting for a container to run them. I can make many containers using the same image.

## How it connects
- [[Containers vs Virtual Machines]] — a container is the running instance described here
- [[Kernel]] — the container process still ultimately runs on the one shared host kernel

## Where it's used
One of the most common Docker interview questions ("what's the difference between an image and a Dockerfile / container?"). Chain: **Dockerfile → `docker build` → Image → `docker run` → Container**.

## Gotchas
- First-pass mistakes that got corrected in this lesson:
  - The Dockerfile only defines *how to build one image* — it does **not** define a CI/CD pipeline. A CI/CD pipeline (e.g. GitHub Actions YAML) is a separate config that *uses* the Dockerfile as one step ("build the image, then push/deploy it").
  - The image itself is **not running** — that's the container. The image is an inert, built artifact (a stack of read-only layers) sitting on disk until `docker run` creates a container from it.
- Recipe analogy: Dockerfile = recipe (instructions), Image = a frozen meal made from that recipe (built once, inert, stored), Container = the meal actually in the microwave right now (running).
