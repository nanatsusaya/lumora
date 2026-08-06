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
`08 Writing` or `05 Story Architecture`. The work of the last six weeks before
this adoption was prose, not worldbuilding.

Opened file by file on 2026-08-06, because the first version of this section was
written from a directory listing and got it wrong:

| Where | What is in it |
|---|---|
| `08.00 Entwürfe`, ch. 1-5 and 11-13 | real prose, 11 KB to 217 KB; ch. 5 alone runs 2,127 lines |
| `08.00 Entwürfe`, ch. 6-10 | outline only, 16 to 26 lines |
| `08.01 Fertig`, ch. 1-3 | **empty** - 110 bytes each, `TODO` under both language headings |

**No chapter is finished.** `08.01 Fertig` holds three placeholder files. The
earlier wording here - *chapters 1 to 3 have a version under `08.01 Fertig`* -
was inferred from three filenames in a folder called *Fertig*, and no file was
opened to check it.

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
| Frontmatter on every note | 0001 | ❓ accepted; 4 of 140 notes have none |
| One `*Tag:*` per section | 0001 | ❓ accepted; one section carries two |
| Tag vocabulary | 0002 | ❓ accepted; 11 of 140 reference notes carry no kind or maturity tag |
| ASCII slugs for tags | 0004 | ❓ accepted; one tag disagrees with it |
| EN gloss, tone, file editing, glossary | 0003, 0005, 0006, 0007 | ✅ in force (2026-08-06) |
| Prose off the maturity axis, no checks over content | 0008 | ✅ in force (2026-08-06); nothing to change |

The four ❓ rows are what writing the records produced: each convention was
measured against the vault for the first time, and none of them is fully
followed. The records say what holds; bringing the notes in line is separate
work and is not started.

## Open questions for the deciders

None open.

*O1 - prose or worldbuilding as the primary focus - answered 2026-08-06:
neither, they carry equal weight. Folded into* Where we stand *above.*

*O2 - do the remaining conventions in `CLAUDE.md` become decision records -
answered 2026-08-06: yes, one record each, in the order the index listed them.
All six are written and* Accepted*; the index has no* Planned *row left.
Daniel reserved judgment on the result -* „ich schau mir an was es bewirkt und
entscheide später ob es mir gefällt" *- so a later decision to undo or reshape
this is expected, and would be a superseding record rather than an edit.*

## Next step

Take Part I chapter 1 from `08 Writing/08.00 Entwürfe` to `08.01 Fertig` - the
file waiting there is an empty placeholder and the draft behind it runs 278
lines - and write into `02 Worldbuilding` whatever that chapter had to settle
about the world. That is the equal weighting applied to the next concrete piece
of work rather than stated as a principle.

If that is blocked, the decision-free work is `02 Worldbuilding/02.04 Religion &
Götter`, `02.05 Geschichte` or `02.06 Konflikte`. All three hold nothing but
their folder overview note, and none of them needs a decision from anybody.
