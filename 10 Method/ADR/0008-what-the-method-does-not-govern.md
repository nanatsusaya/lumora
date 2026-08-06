---
tags:
  - meta
---
# 0008: What the method governs, and what it leaves alone

**Status:** Accepted · Decided 2026-08-06

## Context

Record 0002 puts every note on a maturity axis. Measured against the vault it
produced 21 notes carrying neither `wip` nor `ready`, and ticket #5 was filed to
bring them in line. Ten of those 21 are the Part I chapter drafts in
`08 Writing`.

Daniel, after merging the adoption:

> ich will die inhalte des projekts nicht zu genau mit tests abdecken, da es ein
> freier kreativer text ist der langsam aber stetig wachsen soll und nicht durch
> zuviel tests begrenzt werden soll

That is not an objection to 0002. It names a boundary none of the records drew:
they were written about the vault as a reference apparatus and then applied to
the novel as well, because nothing said where one stops and the other starts.

What `08 Writing` actually holds, measured file by file on 2026-08-06:

| Where | Maturity tag | Size |
|---|---|---|
| `08.00 Entwürfe`, ch. 1 and 3-13 | none | 491 bytes to 217 KB |
| `08.00 Entwürfe`, ch. 2 | `- "#wip"` | 35 KB |
| `08.01 Fertig`, ch. 1-3 | `wip` | 110 bytes each, both sections `TODO` |

Three treatments in one folder, and the only place the tag is applied
consistently is three empty placeholder files. A `wip` that sits on a 110-byte
stub and on a 2,127-line chapter alike distinguishes nothing.

## Decision

**The method governs how work is done here. It does not govern the story.**

**1. Prose in `08 Writing` carries no maturity tag.** Whether a chapter is
finished is said by the folder it sits in - `08.00 Entwürfe` or `08.01 Fertig` -
and a tag repeating that is a second place to keep in sync. The maturity axis of
0002 applies to the reference notes: `00`-`07`, `09`, `10`. Subject tags
(`part-1`, `protagonist`) are unaffected, and 0001 is untouched - every note
still needs frontmatter with at least one tag.

**2. No check is added over the content of Lumora.** Not over canon
consistency, not over the Noetic rules, not over prose. The checker reads
`method.json`, the four artifacts, ordinary Markdown references and one spelling
regime, and that stays its reach. Whether the world holds together is read and
argued, not asserted by a run that passed.

## Consequences

**Ticket #5 drops from 21 notes to 11**, none of them prose: four notes with no
frontmatter at all, four in `07 Research`, and `00 Inbox/Sprüche & Ideen.md`,
`05 Story Architecture/05.03 Erzählperspektiven.md`,
`06 Lore & Mystery/__Lore & Mystery.md`.

**The count is 140, where earlier records say 138.** Today's scan is every `.md`
file under the vault root except `.git`, `.github`, `.claude`, `Assets` and
`10 Method`, and except `CLAUDE.md` and `README.md`. The earlier figure was
taken with a boundary that was never written down, so which two notes account
for the difference cannot be recovered. That is the point rather than an aside:
a measurement without its rule is not reproducible, and a number in a record has
to be. Records 0001 to 0007 keep their 138; from here the boundary above is the
one in use.

**Whether a chapter is done becomes a fact about a folder.** Moving the file is
the act, there is nothing else to update, and nothing that can disagree with it.
No tag filter answers "show me the finished chapters" - `08.01 Fertig` is the
answer, and it is one click.

**This buys silence in one direction, and it is worth naming.** Nothing will
report that a draft went stale, that a chapter contradicts `02 Worldbuilding`,
or that a scene promised in an outline was never written. None of that was
detected before either, and this record does not make it detectable. What it
buys is that no rule claims to.

**A later check over content needs a superseding record**, not an addition made
in passing because something looked easy to verify.

## Alternatives considered

**Tag the drafts `wip` and promote them on the move to `08.01 Fertig`.**
Rejected: two authorities for one fact, which is the defect C2 names. Folder and
tag disagree the moment one is updated without the other, and the folder is the
one that actually gets moved. The three files in `08.01 Fertig` are the proof -
tagged `wip`, sitting in the folder called finished, and empty.

**A third maturity value for prose.** Rejected: it would be a synonym for the
folder name.

**Exempt `08 Writing` in the ticket and write nothing down.** Rejected: the next
session reads 0002, measures the vault, finds ten untagged drafts and files the
same ticket. Preventing exactly that is what a record is for.

**Take `08 Writing` out of the checker's reach through `ignore`.** Rejected for
the reason already in the method log: `ignore` removes a document from every
check, not from one, and that is how the neighboring project lost its link
coverage for weeks. Nothing checks the prose for its content today; removing it
from the scans would only drop the spelling and reference checks, which do no
harm where they are.
