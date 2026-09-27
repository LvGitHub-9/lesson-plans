# Lesson Plans

[中文](README.md) | **English**

> Turning courses, talks and video series into **teachable, testable, traceable** lesson plans.
> Every knowledge point comes with pre-test questions, exercises, answers, common
> misconceptions and mastery criteria — not a course summary.

⚠️ Each lesson plan is a **derivative work** of its source material and follows that
source's license (usually CC BY-NC 4.0). **Attribution and licensing are listed per course.**
See [NOTICE.md](NOTICE.md).

---

## Courses

| Course | Source | Lectures | Points | License | Directory |
|---|---|---|---|---|---|
| **Generative Software Engineering** | Nanjing University, Fall 2026 · Yanyan Jiang | 6 | 99 | CC BY-NC 4.0 | [`courses/gse-2026/`](courses/gse-2026/) |

<!-- When adding a course, add a row here and create a directory under courses/ -->

## The format

Every knowledge point is expanded into the same **11 fields**
(full spec in [TEMPLATE.lesson.md](TEMPLATE.lesson.md)):

| Field | Purpose |
|---|---|
| **Atomicity** | Tests exactly one thing (otherwise split it) |
| **Original text** | With section anchor — **points back to the source** |
| **Mechanism / why** | If the material doesn't give one, it says **"gap"** — no fabrication |
| **Prerequisites** | Which point this depends on (materials almost never state these) |
| **Standard example** | Minimal and reproducible — not a scenario description |
| **Common misconceptions** | Listed explicitly |
| **Applicability limits** | When it does *not* hold |
| **Pre-test questions** | Asked **before** teaching (pre-testing beats post-testing) |
| **Exercises + answers** | Increasing difficulty, verifiable answers |
| **Transfer task** | A different context |
| **Mastery criteria** | Can explain / can apply / can recall |

**Why this format.** The usual "AI summarizes a course" output is a **summary** — fluent,
but useless for learning. A summary can't be tested against, so it never exposes the
fluency illusion (feeling you understand it, then being unable to recall any of it).
Turning material into questions is what makes learning actually happen.

## How to use it

1. **Read the course overview first** (`overview.lesson.md`) — it contains the dependency
   graph, **cross-lecture concept threads**, and learning paths.
   A course spirals: the same criterion reappears across lectures. Learning lecture-by-lecture
   fades; following a concept thread sticks.
2. **Enter a lecture and take the pre-test first** (don't read the explanation yet).
3. Read "original text + mechanism", do the exercises, then self-check against **mastery criteria**.
4. For anything the material doesn't settle, read the **gap summary** — those are
   explicitly marked boundaries, not omissions.

## Adding a course

1. Copy [`TEMPLATE.lesson.md`](TEMPLATE.lesson.md) and fill in the 11 fields
2. Create `courses/<slug>-<year>/` with the lesson plans plus a course `README.md`
   (containing **that course's own attribution and license**)
3. Update the table above and the attribution table in `NOTICE.md`
4. For a multi-lecture course, also write an `overview.lesson.md`
   (the pattern is described at the end of the template)

**Pipeline** (full version in the template):

```
① Find a text source (notes / course site / blog / textbook)  ← highest priority
② Platform AI subtitles (logged in)                          ← the "explanation" layer
③ Local ASR with a domain glossary                           ← a second, independent transcript
④ Cross-validate the two transcripts → keep only term-level disagreements
⑤ Extract frames and read them                               ← only if ① and ② don't cover it
⑥ Split into atomic points → 11 fields → lesson plan
```

**Three disciplines** — this is what separates this library from "course notes":

1. **Traceability**: every point must point back to a section / page / timestamp.
   If it can't, it was invented.
2. **Three source markers**: `【原话】` / `【外部补充】` / `【待查证】` never mixed.
3. **Gaps are written as gaps**: if the material gives no mechanism, no boundary, no answer,
   say so. **Better to leave a blank than to invent a plausible-sounding explanation.**

## Branch convention

- `main` — finished, generalized lesson plans (readable as-is)
- `draft/<course>` — work-in-progress (incomplete / not yet generalized), not meant to be read

> Multiple courses are organized as **directories**, not branches: branches can't be browsed
> or searched together, and every course would duplicate the shared files.

## License

Each course's lesson plans follow **their own source material's license**, listed per course
in [`NOTICE.md`](NOTICE.md) and in each course's `README.md`.

**All courses currently included are CC BY-NC 4.0**: share and adapt freely with attribution,
❌ **no commercial use**.

If you are the rights holder of any source material in this library and object to the
attribution or the content, please open an issue — I will adjust or remove it immediately.

## Related

The personal learning data (original, non-generalized lesson plans; learning state; session
logs) lives in a separate **private** repository. The lesson plans here are **generalized**
from that private version — personal knowledge profile removed, methodological setup kept.
