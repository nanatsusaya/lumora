---
tags:
  - meta
---
# 0001: Frontmatter and section format

**Status:** Accepted · Decided 2026-08-06 (recording a practice in force since
the vault was created)

## Context

The vault is read and written by two kinds of author: Daniel, and AI agents that
arrive with the repository and no memory of earlier sessions. Both need to know,
without asking, whether a note is finished, what a section is called elsewhere
in the vault, and which term is a coined name rather than an ordinary heading.

The vault has answered this from the start with a fixed shape for frontmatter
and for named sections. It works, it is applied nearly everywhere - measured
2026-08-06, 134 of 138 vault notes carry frontmatter - and it had never been
written down as a decision, only as instructions inside `CLAUDE.md`. That is
enough to follow the rule and not enough to know why it holds, which is what
makes a rule get dropped.

## Decision

**Every note carries YAML frontmatter with at least one tag.**

```
---
tags:
  - wip
---
```

Which tags exist and what each of them claims is **0002**. This record requires
only that the frontmatter is there and carries at least one.

**Every named section with its own heading carries a three-line block directly
below the heading:**

```
### Name der Sektion
*EN: English Name*        <- only for coined terms
*Tag:* #section-id        <- exactly ONE tag, the unique section identifier
*Status:* #wip            <- one or more status flags
```

- `*Tag:*` is always exactly one tag. Two tags there means the section is two
  sections.
- `*Status:*` may combine flags: `#wip`, `#ready`, `#working-title`.
- `#working-title` belongs in `*Status:*`, never in `*Tag:*`.
- The progression is `#wip` then, when complete, `#ready`.

**The `*EN:*` line is not on every heading.** Which headings earn one is **0003**.

**All tag identifiers and status flags are English**, never German: `#primal-god`,
`#hakani`, `#desert-of-tears`, `#n-force`. Names carrying letters ASCII does not
have are **0004**.

## Consequences

A note without frontmatter is incomplete, not merely untidy: Obsidian's tag pane
and every search that filters by maturity silently skip it, so it looks absent
rather than unfinished. **Four notes are in that state**, measured 2026-08-06:
`00 Inbox/Entwürfe Part I.md`, `00 Inbox/Prosa-Beispiele.md`,
`02 Worldbuilding/02.02 Spezies/Kulturschaffende/Kulturschaffende Spezies.md`
and `03 Noetic System/03.09 Innerweltliche Fehlinterpretation.md`. The third is
the peoples overview that `CLAUDE.md`'s own *Key Files to Read* table sends
readers to. Nothing reported this until the record was written and the vault was
counted against it.

`ready` is a claim about the whole note. Promoting a note while one of its
sections is still `wip` makes the tag mean nothing, and the next reader has no
cheaper way to find out than reading the note.

**One `*Tag:*` line breaks the one-tag rule.** Measured 2026-08-06 across 101
`*Tag:*` lines in the vault, exactly one carries two:
`03 Noetic System/03.02 Funktionsweise.md:134` reads `*Tag:* #fringe */* #void`.
Two tags there means the section is two sections, and a cross-reference to it
resolves to whichever the reader picks. Nothing reported it; the rule had never
been counted against the vault before this record was written.

The three lines are not independent. A heading that earns an `*EN:*` line under
0003 also earns a `Glossar.md` entry under 0007, in the same work step, and a
`*Tag:*` built from a name with special letters takes the slug from 0004. This
record fixes the shape; three others fill it.

Sections are addressed across the vault as `[[Note#Heading|Display]]`. Renaming
a heading therefore breaks incoming links, and nothing in this repository checks
that: the method's reference check reads ordinary Markdown links — 51 of them on
2026-08-06 — and ignores the 1,892 `[[wiki-links]]`. Obsidian catches a rename
while the vault is open; a rename made outside Obsidian does not get caught at
all.

## Alternatives considered

**Frontmatter fields instead of a text block per section.** YAML cannot be
attached to a section, only to a file, so this would mean one note per section.
The vault deliberately groups related sections in one note - a species, its
biology, its culture, its use of the Noetic Force - and splitting them would
scatter what is read together.

**Dropping the `*Tag:*` line and relying on headings.** Headings change wording
while the concept stays; the tag is the stable identifier that survives a
rewrite. Removing it would make every cross-reference depend on a phrasing
nobody promised to keep.
