---
tags:
  - meta
---
# Decision records

Binding decisions about how this vault is written and structured. One record
holds one decision: what was decided, why, and what was rejected. Records are
append-only - a decision that no longer holds is superseded by a new record, not
edited away, because the reason an old rule existed is what stops the next
session from re-deciding it badly.

**These are decisions about the vault, not about Lumora.** In-world truths -
the canon laws, the Noetic rules, cosmology - are content and live in
`01 Kern von Lumora` and `02`-`03`. The test: a canon law would stop holding if
Lumora told a different story; a record here would still hold.

## Status values

- **Proposed** - written, waiting for approval
- **Accepted** - in force, binding for every note
- **Superseded** - overtaken by a later record, kept for its reasoning
- **Planned** - decided that it needs a record, not yet written

A `Planned` row has no file yet, and that is the point: it makes the remaining
work visible without creating an empty document that reads as if something had
been decided.

## Format

Every record is named `NNNN-short-title.md` (four digits, consecutive) and
carries a status line and four sections in this order:

1. `## Context` - where the question came from
2. `## Decision` - what holds
3. `## Consequences` - what follows from it, the uncomfortable part included
4. `## Alternatives considered` - what was rejected, and why

The status in the record and the status in the index below have to agree. That
is checked.

## Index

| Nr. | Decision | Status |
|---|---|---|
| 0001 | [Frontmatter and section format](0001-frontmatter-and-section-format.md) | Accepted |
| 0002 | [Tag vocabulary](0002-tag-vocabulary.md) | Accepted |
| 0003 | [When a heading gets an `*EN:*` gloss](0003-en-gloss-for-coined-terms.md) | Accepted |
| 0004 | [ASCII slugs for tags of names with special letters](0004-ascii-slugs-for-tags.md) | Accepted |
| 0005 | [Factual tone in reference notes, and its exceptions](0005-factual-tone-in-reference-notes.md) | Accepted |
| 0006 | [File editing through Python, and verification in the same step](0006-file-editing-and-verification.md) | Accepted |
| 0007 | [Glossary upkeep alongside every new coined term](0007-glossary-upkeep.md) | Accepted |

All seven record conventions the vault already followed. None of them changes
what a note must look like; what they add is the reason, which is the part that
was only ever in somebody's head. `CLAUDE.md` now states each rule and names its
record instead of explaining it twice.

Writing them down measured the vault against them for the first time, and the
measurements are in the records: four notes without frontmatter (0001), 21 of 138
notes invisible to a maturity filter (0002), one tag spelled `#luminæri-lady`
where the rule says `#luminaeri-lady` (0004), one `*Tag:*` line carrying two tags
(0001). None of that is fixed here — the records say what holds, and bringing the
vault in line is separate work.
