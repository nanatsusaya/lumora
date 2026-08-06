---
tags:
  - meta
---
# Status and next steps

> Living handoff note between sessions. Last updated: **2026-08-06**.
> Binding decisions live in [[ADR]]; this file records progress only.
> Stable working rules live in `CLAUDE.md`.

## Maturity

So that "decided" is never read as "built", every area sits at one of:

- **planned** - named, not yet worked on
- **designed** - an accepted decision exists, nothing written
- **draft** - written and visible, not complete or verified
- **complete** - finished and checked against its own criteria
- **live** - published

**An accepted decision is `designed`, not `written`.**

## Where we stand

| Area | Folder | Maturity |
|---|---|---|
| Core philosophy and canon | `01 Kern von Lumora` | complete |
| Noetic system: basics, mechanics, limits | `03 Noetic System` | complete |
| Cosmology and world structure | `02 Worldbuilding/02.01` | draft |
| The twelve culture-bearing peoples | `02 Worldbuilding/02.02` | draft |
| Peoples and societies in depth | `02 Worldbuilding/02.03` | draft |
| Religion, history, conflicts | `02 Worldbuilding/02.04-02.06` | planned |
| Characters | `04 Characters` | draft |
| Story architecture, Part I-V | `05 Story Architecture` | draft |
| Lore and mystery | `06 Lore & Mystery` | draft |
| Prose, Part I | `08 Writing` | draft |
| Geography: regions and hotspots | not yet created | planned |
| Full timeline | not yet created | planned |
| Working method | `10 Method` | draft |

**What the repository actually shows.** The last commit before this adoption is
`de92cb1`, dated 2026-07-06. Every commit from 2026-06-24 onward touches
`08 Writing` or `05 Story Architecture`: chapter drafts 1 to 13 of Part I exist
under `08.00 Entwürfe`, and chapters 1 to 3 have a version under `08.01 Fertig`.
The work of the last six weeks before this adoption was prose, not
worldbuilding.

`CLAUDE.md` said otherwise until today. It carried *Last updated: 2026-06-23*
and named the deepening of the peoples as the primary focus, and `README.md`
repeated it. Both now point here instead.

**Prose and worldbuilding carry equal weight (decided 2026-08-06).** The novel
is the goal; the worldbuilding is the condition for writing it, and neither
works without the other. Neither is therefore the *primary* one, and the six
weeks of prose were not a detour from the plan - the plan was wrong about
itself. In practice: a chapter is written, and whatever that chapter had to
settle about the world is written into `02` in the same stretch of work.
Not deferred to a worldbuilding phase that never arrives, and not invented in
the prose and left there.

## Decided but not yet in force

| What | Decision | State |
|---|---|---|
| Frontmatter tag and section format | 0001 | ❓ accepted, never checked across all 144 notes |
| The remaining conventions in `CLAUDE.md` | 0002-0007 | ⛔ needs a decision record each |

## Open questions for the deciders

**O2 - Do the remaining conventions in `CLAUDE.md` become decision records?**
For Daniel. Six of them stand as `Planned` rows in [[ADR]]: the tag vocabulary,
the `*EN:*` gloss rule, the ASCII tag slugs, the tone in reference notes, the
file-editing rules, and glossary upkeep. Each works today and none of them says
*why* it holds, which is what makes a rule get dropped by a session that finds
it inconvenient. Recommended: yes, one record each, in that order - after which
`CLAUDE.md` states each rule in a line and names its record instead of
explaining it twice. Nothing is blocked on this.

*O1 - prose or worldbuilding as the primary focus - was answered on 2026-08-06:
neither, they carry equal weight. The answer is folded into* Where we stand
*above.*

## Next step

Take Part I chapter 4 from `08 Writing/08.00 Entwürfe` to `08.01 Fertig` -
chapters 1 to 3 are already there - and write into `02 Worldbuilding` whatever
that chapter had to settle about the world. That is the equal weighting applied
to the next concrete piece of work rather than stated as a principle.

If that is blocked, the decision-free work is `02 Worldbuilding/02.04 Religion &
Götter`, `02.05 Geschichte` or `02.06 Konflikte`. All three hold nothing but
their folder overview note, and none of them needs a decision from anybody.
