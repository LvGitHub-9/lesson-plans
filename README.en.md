# Generative Software Engineering (Fall 2026) — Lesson Plans

[中文](README.md) | **English**

> Turning the 6-lecture course *Generative Software Engineering* (Nanjing University, Fall 2026)
> into **teachable, testable, traceable** lesson plans — every knowledge point comes with
> pre-test questions, exercises, answers, common misconceptions, and mastery criteria.
> Not a course summary.

⚠️ **This repository is a derivative work of course content licensed CC BY-NC 4.0
(attribution + non-commercial).** See [Attribution](#attribution).

---

## What this is

Most "AI summary of a course" output is a **summary** — fluent, but useless for actually
learning. These lesson plans have a different goal: **turn the course into material you can
test yourself against.**

Every knowledge point (**99 in total**) is expanded into the same 11 fields:

| Field | Purpose |
|---|---|
| **Atomicity** | Tests exactly one thing (otherwise split it) |
| **Original text** | With section anchor, pointing back to the source |
| **Mechanism / why** | If the material doesn't give one, it says **"gap"** explicitly — no fabrication |
| **Prerequisites** | Which point this depends on (courses almost never state these) |
| **Standard example** | Minimal, reproducible — not a scenario description |
| **Common misconceptions** | Listed explicitly |
| **Applicability limits** | When it does *not* hold |
| **Pre-test questions** | Asked **before** teaching (pre-testing beats post-testing) |
| **Exercises + answers** | Increasing difficulty, verifiable answers |
| **Transfer task** | A different context |
| **Mastery criteria** | Can explain / can apply / can recall |

## Contents

| # | Lecture | IDs | Points | Lesson plan |
|---|---|---|---|---|
| — | **Course overview** | — | — | [Overview](lessons/gse-course-overview.lesson.md) |
| 01 | Welcome to the Future | `S1–S19` | 19 | [Plan](lessons/gse-lecture-01.lesson.md) |
| 02 | Prompt & Context Engineering | `T1–T15` | 15 | [Plan](lessons/gse-lecture-02.lesson.md) |
| 03 | Version Control (1) | `U1–U17` | 17 | [Plan](lessons/gse-lecture-03.lesson.md) |
| 04 | Version Control (2) | `V1–V14` | 14 | [Plan](lessons/gse-lecture-04.lesson.md) |
| 05 | Where Software Engineering Came From | `W1–W17` | 17 | [Plan](lessons/gse-lecture-05.lesson.md) |
| 06 | Requirements & Architecture (1) | `X1–X17` | 17 | [Plan](lessons/gse-lecture-06.lesson.md) |

> The lesson plans are written in Chinese (the course language).

**Where to start**
- For the big picture → the overview's **§3 cross-lecture concept threads**
- For one concrete point → [L1 §S15 "Locality of change"](lessons/gse-lecture-01.lesson.md),
  which connects to the classic idea of *change amplification* / *tar pit*

## How these were made

The core question was **what counts as "the original text"**:

```
① Find a text source (course notes / course site)   ← highest priority
② Fetch the platform's AI subtitles (logged in)     ← the "explanation" layer
③ Local ASR with a domain glossary                  ← a second, independent transcript
④ Cross-validate the two transcripts → keep only term-level disagreements
⑤ Extract frames and read them                      ← only if ① and ② don't cover it
⑥ Split into atomic points → 11 fields → lesson plan
```

Notable practices:

- **Three layers of "original text", ranked by reliability**: course notes (★★★) >
  on-screen content (★★) > speech transcript (★). **When notes exist, the section anchor is
  the primary citation; timestamps are auxiliary** — videos get re-edited, timestamps rot.
- **Two independent ASRs, cross-validated.** Measured: their errors are *complementary* —
  one systematically fails on English identifiers (`main` → a Chinese homophone), the other
  on homophone technical terms. Where they agree, trust it; where they disagree, one frame
  settles it.
- **Collapse repair**: in 5 of the 6 lectures the local ASR entered a repetition loop
  (emitting a stream of "I, I, I…") and **silently lost content**. Two ASRs don't collapse
  at the same time, so collapsed ranges are patched from the other transcript.
  A single ASR **will** silently drop content.
- **Using the lecturer's real in-class questions as pre-tests.** Course notes often say
  "the class was asked…" — those fit the course designer's intent far better than invented
  questions (20+ such uses here).
- **Gaps are written as gaps.** Where the material gives no mechanism, no boundary, or no
  answer, the lesson plan says so instead of inventing a plausible-sounding explanation.

## Reading notes

- `【讲义原话】` — explicitly stated in the course notes (with section anchor)
- `【视频】` — spoken in class
- `【讲义原话·课堂提问】` — a question the lecturer actually asked in class
- `【外部补充】` — **added by the lesson-plan author**, not in the course notes
- `【待查证】` — unverified (the course notes cite many external sources; not individually checked)

Every lecture ends with a **gap summary** — an explicit list of what the material does not
settle, rather than fields filled in for completeness.

## Who these were written for

These are not generic. They were written for **a learner from a C / microcontrollers /
embedded background**, and heavily rewritten accordingly:

- **No object-oriented prerequisites assumed** — OO concepts (e.g. design-by-contract)
  are rewritten as C functions and structs
- **Domain concepts from courses the learner hasn't taken are expanded**
  (operating systems / networking / databases / compilers)
- **English terms get Chinese glosses**
- **Analogy pool limited to**: signals & systems, motor control / FOC, embedded &
  hardware debugging, C engineering practice, communications
- **Analogies avoided**: data structures, AI/ML, large-scale architecture & design patterns

> If you come from a different background, the interesting part is *how* the same material
> was adapted to a different reader — the criteria and questions transfer directly;
> the examples need replacing with your own domain.

## Attribution

This repository is a **derivative work** of:

- **Course**: Generative Software Engineering (生成式软件工程), Nanjing University, Fall 2026
- **Lecturer**: Yanyan Jiang (蒋炎岩)
- **Course site**: <https://jyywiki.cn/GSE/2026/>
- **Videos**: Bilibili creator 「绿导师原谅了你」 (<https://space.bilibili.com/202224425>)
- **Original license**: CC BY-NC 4.0

Quoted text marked `【讲义原话】` comes from the course notes; `【讲义原话·课堂提问】`
comes from the lectures. **Copyright of the original material belongs to the original author.**

## License

Licensed under **[CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)**:

- ✅ Share and adapt freely (with attribution)
- ❌ **No commercial use**

See [LICENSE](LICENSE) and [NOTICE.md](NOTICE.md).

## Notes

The course has 6 lectures plus one lab (Lab1 "Personal Digital Assistant",
folded into Lecture 04's transfer tasks). The overview's §9 documents how to update
incrementally when the course publishes new lectures.
