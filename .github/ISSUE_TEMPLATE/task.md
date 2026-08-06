---
name: Work ticket
about: One self-contained piece of work on the vault or on how it is worked
title: ''
labels: task
---

<!--
Agents write the tickets here too, so a ticket is held to the same bar as the
work. The readiness section is not ceremony: an agent given an under-specified
ticket fills the gaps by inference rather than by asking, and the inference is
invisible in the result.

Language: English - this is project steering. The names of vault files, notes,
sections, tags and coined terms stay German, because that is what they are
called. See method.json.

This is for work on the project. Ideas about the *world* - lore, species,
characters, story logic - belong in one of the other forms, or in the Discord.
-->

## Context

<!-- The problem or goal, and why it exists. Enough that someone with this
     repository and nothing else can act on it. Name the notes involved by
     their real paths. -->

## Scope

<!-- For a decision: the choices that have to be made.
     For work on the vault: testable acceptance criteria, one per line. -->

- [ ] «criterion»

## Constraints

<!-- Anything that limits the solution. Standing ones worth naming when they
     apply: `01 Kern von Lumora` does not change to solve a story problem; the
     Elværin naming and the esteem scale in Waldelværi.md are the single source
     of truth for species names; a new coined term needs a Glossar.md entry in
     the same step. -->

## Related

<!-- Parent epic, related decision records in `10 Method/ADR/`, other tickets. -->

---

**Ready** when: the scope above is concrete, the criteria are testable, and the
constraints are named.

**Done** when: the criteria are met **and verified**; every written file was
read back in full with no null bytes; work and documentation changed together;
`10 Method/STATUS.md` reflects it if it changed where we stand; the change is
merged.
