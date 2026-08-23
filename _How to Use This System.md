---
tags: [meta]
---
# How to Use This System

This vault is wired to Claude Code (via the `obsidian-study` skill) and to your Linear curricula (TypeORM Mastery, Frontend Mastery, AI Mastery Curriculum). This note is the human-facing "how do I actually drive this" guide — check back here whenever you forget the flow.

## 1. Starting a session

Open any Claude Code chat (doesn't have to be this project) and just say one of:

- **"Let's study TYP-31"** / **"next lesson in TypeORM Mastery"** — pulls the lesson from Linear
- **"Teach me connection pooling"** — freeform, no Linear issue needed
- **"What's due for review today?"** — pulls up your spaced-repetition queue
- **"Quiz me on what's due"** / **"quiz me on lessons 1-10"** — active recall session

No setup per session — it's a standing skill, always available.

## 2. What happens during a lesson (don't skip step 2!)

1. Claude explains the concept.
2. **You explain it back, in your own words, or answer a check question.** This is not optional and not skippable — it's the single biggest lever for actually remembering this later. A note Claude writes alone is filing, not learning.
3. Claude writes a
4. tomic notes + a Canvas mind map from *your* explanation, links everything, updates the curriculum index.
5. When you say you're done, the Linear issue gets marked Done and spaced-repetition tracking starts on the new notes.

> [!warning] What happens if you skip step 2
> See [[TypeORM/7 - Relations OneToOne and ManyToMany]] — that's a real note from this vault. The recall question got a "continue" instead of an answer, so it's sitting there with `[!PLACEHOLDER]` blocks instead of real content. It won't get quizzed meaningfully and won't stick, because there's nothing real in it yet. **Open it, actually answer the question this time, and watch the placeholder get replaced** — that's the fastest way to feel the difference.

## 3. Where things live

- [[_Topic Map]] — which folder each curriculum's lessons go into (existing folders like `React/`, `JavaScript/` get reused; only genuinely new subjects like `TypeORM/` or `AI/` get their own folder)
- `_<Curriculum> Index.md` (e.g. [[_TypeORM Mastery Index]], [[_Frontend Mastery Index]], [[_AI Mastery Curriculum Index]]) — one per curriculum, table of every lesson + status + links
- [[_Study Dashboard]] — **check this first each session** — links to every index + what's due today
- [[_Weak Spots]] — notes you've gotten wrong repeatedly; 3+ misses = flagged chronic, offered a re-teach

## 4. Using Obsidian's own UI (not just chat)

- **Graph View** → filter by `tag:#<topic>` (e.g. `tag:#typeorm`) to see everything you've built on that subject as a connected cluster.
- **Canvas files** (`Canvases/…canvas`) → double-click in the file explorer to open the visual mind map for one lesson. Click any box to jump straight to the real note behind it.
- **Backlinks panel** (bottom of any note) → see everything else that links to the note you're viewing — this is how you discover a concept resurfacing in a different curriculum.

## 5. The one rule that matters most

**Looking at the graph or the canvas is not reviewing.** It's easy to click through a pretty mind map, feel like you understand it, and not actually retain anything — that's the illusion of competence. The graph is the map. **Quiz mode is the actual rehearsal.** If you only have five minutes, spend them on a quiz, not on browsing.

## 6. Quiz mode specifics

- Questions are asked as open recall ("what happens when the pool is exhausted?"), not multiple choice — answer before anything is revealed.
- When reviewing what's due across multiple curricula, questions come **interleaved** (mixed topics), not blocked one curriculum at a time — this is deliberate, mixed practice sticks better than one big TypeORM block followed by one big React block.
- Get it right → the note's review interval grows (1 day → 3 → 7 → 14 → 30). Get it wrong → resets to tomorrow and logs to [[_Weak Spots]].

## 7. Try it now

You already have one lesson sitting half-finished: [[TypeORM/7 - Relations OneToOne and ManyToMany]] (plus its two linked concept notes, [[TypeORM/JoinColumn Ownership]] and [[TypeORM/Explicit Junction Entities]]). Open a Claude Code chat and say **"let's finish TYP-11"** — this time, actually answer the recall question. That's the whole system, end to end, on real content.
