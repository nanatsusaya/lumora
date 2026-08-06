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
| 0002 | Tag vocabulary and what each tag means | Planned |
| 0003 | When a heading gets an `*EN:*` gloss | Planned |
| 0004 | ASCII slugs for tags of names with special letters | Planned |
| 0005 | Factual tone in reference notes, and its exceptions | Planned |
| 0006 | File editing: UTF-8 through Python, and post-write verification | Planned |
| 0007 | Glossary upkeep alongside every new coined term | Planned |

Rows 0002 to 0007 are conventions `CLAUDE.md` already prescribes and enforces.
They are listed as `Planned` because the reasoning behind them is not written
down anywhere, and a rule without its reason is the one a later session drops.
Moving them here is the work O2 in [[STATUS]] asks about.
