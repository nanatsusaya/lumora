---
tags:
  - meta
---
# 0002: Tag vocabulary

**Status:** Accepted · Decided 2026-08-06 (recording a practice in force since
the vault was created)

## Context

Obsidian's tag pane, its search and its graph are the only navigation this vault
has over 138 notes. Three things have to be readable without opening a note:
whether it is finished, whether it may be changed at all, and whether it is
about the story or about the vault.

`CLAUDE.md` has named four tags from the start — `canon`, `wip`, `ready`,
`meta` — in a single table. What it never said is whether that list is
exhaustive, or how those four relate to the tags notes also carry for their
subject. It reads as one flat vocabulary, and the vault does not use it that
way.

Measured across the 138 vault notes on 2026-08-06: `wip` on 105, `ready` on 11,
`canon` on 8, `meta` on 4 — and **11 notes carry two of them**, which under a
flat reading looks like an error and is not one. Alongside them stand 36
distinct subject tags: `species`, `spoiler`, `part-1`, `protagonist`,
`primary-god`, and thirty more.

## Decision

The four tags answer **two** questions, and a note may answer both.

**What kind of note is this?**

| Tag | Meaning | Applied to |
|---|---|---|
| `canon` | Inviolable foundation. Never removed. | every note in `01 Kern von Lumora` |
| `meta` | Describes the vault itself, not story content | `09 Meta/`, `10 Method/` |

A note that is neither — most of the vault — carries neither.

**How finished is it?**

| Tag | Meaning |
|---|---|
| `wip` | in progress |
| `ready` | complete — and only when **every** section in the note is `ready` (see 0001) |

The two combine, and that combination is intended, not an oversight: every note
in `01 Kern von Lumora` carries `canon` **and** `ready`, because it is both
untouchable and finished.

**Subject tags are free.** `species`, `spoiler`, `part-1`, `protagonist` and the
rest name what a note is *about*. They are not governed by this record.
`09 Meta/Tags.md` is the reference for which ones exist.

This restates the vocabulary; it does not change it. No note's tags change as a
result of this record.

## Consequences

**The two kinds of tag say different things, and only one of them is a claim
about the note's state.** A reader filtering for `#ready` gets finished notes
whatever they are about. That holds only as long as nobody uses a subject tag to
mean maturity — and `working-title`, on 25 notes, sits close to that line: 0001
has it as a *section* status flag, and it is also in use as a note-level tag.

**Nothing checks any of this, and the vault does not fully follow it.** Measured
2026-08-06:

- **4 notes have no frontmatter at all**, so they carry no tag of any kind. They
  are named in 0001, which is where the requirement that frontmatter exists
  lives.
- **17 more carry frontmatter with subject tags only**, no kind and no maturity.
  Ten of those are the Part I chapter drafts in `08 Writing`, four are in
  `07 Research`, and the rest are `00 Inbox/Sprüche & Ideen.md`,
  `05 Story Architecture/05.03 Erzählperspektiven.md` and
  `06 Lore & Mystery/__Lore & Mystery.md`.

That is **21 of 138 notes invisible to a maturity filter**, which is the one
thing the vocabulary exists to make visible. The rule is not wrong; it was never
measured until this record was written.

**Two spellings are in use.** 18 notes write the frontmatter entry as
`- "#canon"`, the rest as `- canon`. Whether Obsidian resolves both to the same
tag was not verified here. Either way two spellings for one tag is drift, and
the bare form is the one the majority uses.

**A fifth kind or a third maturity value needs a superseding record**, not an
addition made in passing. Four tags are cheap to hold in your head; that is most
of what makes them work.

## Alternatives considered

**One flat list of four, as `CLAUDE.md` states it.** Rejected on the evidence:
eleven notes already carry two, and a flat list makes that read as a mistake to
be cleaned up. Cleaning it up would remove either the fact that `01 Kern` is
finished or the fact that it is untouchable.

**Governing the subject tags too.** Rejected for now. 36 distinct tags over 138
notes, most of them used once. A controlled vocabulary imposed on that is a list
nobody maintains, and an unmaintained vocabulary is worse than none because it
looks authoritative.

**A `status:` field in frontmatter instead of a tag.** Rejected: the tag pane is
what makes maturity visible at a glance and clickable. A field is visible only to
whoever thinks to search for it.

**Removing `canon` from notes that are also `ready`.** Rejected: `canon` is not a
maturity claim. A finished note and an unchangeable one are different facts, and
`01 Kern` is both.
