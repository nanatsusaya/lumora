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
repeated it. Both now point here instead. Which of the two - prose or peoples -
is the intended focus from here is not settled by this file; see O1.

## Decided but not yet in force

| What | Decision | State |
|---|---|---|
| Frontmatter tag and section format | 0001 | ❓ accepted, never checked across all 144 notes |
| The remaining conventions in `CLAUDE.md` | 0002-0007 | ⛔ needs a decision record each |

## Open questions for the deciders

**O1 - Is the primary focus prose or worldbuilding?** For Daniel. `CLAUDE.md`
named worldbuilding for six weeks while every commit went to `08 Writing`. The
recommended default is to write what the repository shows: prose for Part I is
the active work, and the peoples are deepened when a chapter needs them.

**O2 - Do the remaining conventions in `CLAUDE.md` become decision records?**
For Daniel. Recommended: yes, one record each, in the order the `Planned` rows
in [[ADR]] list them - and `CLAUDE.md` then states the rule and names the record
rather than explaining it twice.

## Next step

Answer O1, then update the maturity table to match it.

If that is blocked, the decision-free work is the next chapter draft in
`08 Writing/08.00 Entwürfe` - it needs no decision from anybody and is the work
that has actually been happening.
