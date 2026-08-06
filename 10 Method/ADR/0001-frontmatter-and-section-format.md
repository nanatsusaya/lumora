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
and for named sections. It works, it is applied across all 144 notes, and it has
never been written down as a decision - only as instructions inside `CLAUDE.md`.
That is enough to follow the rule and not enough to know why it holds, which is
what makes a rule get dropped.

## Decision

**Every note carries YAML frontmatter with at least one tag.**

```
---
tags:
  - wip
---
```

The tags in use are `canon` (inviolable foundation, never removed; all notes in
`01 Kern von Lumora`), `wip` (in progress), `ready` (complete - only when every
section in the note is `ready`), and `meta` (describes the vault itself, not
story content).

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

**The `*EN:*` line is added only for coined terms** - invented proper nouns that
will be reused in the English novel, such as species names, god names, and
system terms like *Noetic Force*. Generic headings (Geschichte, Gesellschaft,
Sonnensystem) do not get one.

**All tag identifiers and status flags are English.** Names with special letters
use an ASCII slug in the tag while prose, title and filename keep the letters:
*Elværi* is tagged `#elvaeri`, *Drakōri* is tagged `#drakori`.

## Consequences

A note without frontmatter is incomplete, not merely untidy: Obsidian's tag pane
and every search that filters by maturity silently skip it, so it looks absent
rather than unfinished.

`ready` is a claim about the whole note. Promoting a note while one of its
sections is still `wip` makes the tag mean nothing, and the next reader has no
cheaper way to find out than reading the note.

The `*EN:*` rule creates an obligation elsewhere: a new coined term needs a
matching entry in `Glossar.md`, in both the German and the English section, in
the same work step. That obligation is currently written only in `CLAUDE.md` and
gets its own record (0007).

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

**Glossing every heading in English.** Rejected as noise. A gloss on
*Geschichte* teaches nothing, while a gloss on *Noetische Kraft* is the term the
English novel will use. The rule earns its keep only by being selective.
