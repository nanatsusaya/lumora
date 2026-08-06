---
tags:
  - meta
---
# 0004: ASCII slugs for tags of names with special letters

**Status:** Accepted · Decided 2026-08-06 (recording a practice in force since
the vault was created)

## Context

Four of the twelve culture-bearing peoples carry letters no ordinary keyboard
produces: **Elværi**, **Luminæri** and **Vatæri** carry `æ`, **Drakōri** carries
`ō`. The letters are not decoration. `CLAUDE.md` records them as sung
honor-tones, with `02 Worldbuilding/02.03 Völker & Gesellschaften/Waldelværi.md`
→ *Sprache* as the single source of truth: `-ani` low, `-ari` neutral, `-æri`
respected, `-ōri` revered.

`CLAUDE.md` has required an ASCII slug for the *tag* since the naming was
introduced — `Elværi` is tagged `#elvaeri`, `Drakōri` is tagged `#drakori` —
while prose, titles and filenames keep the letters.

**The reason was never written down.** This record does not invent one. What
follows are the reasons that hold today, checked rather than remembered; if the
original reason was a different one, it is lost and this is what has replaced it.

- **A tag that cannot be typed is not searched.** Neither `æ` nor `ō` is on a
  German keyboard. Filtering by `#elværi` means finding the letter somewhere and
  pasting it.
- **One concept must have exactly one tag.** If both `#elvaeri` and `#elværi`
  exist, a filter returns some of the notes and reports no error. A search that
  quietly answers half the question is worse than one that fails.
- **A tag is an identifier, not prose.** The honor-tone is a fact about the
  language of Lumora and belongs where the language is described and where the
  name is read. The tag only has to point at the same thing every time.

## Decision

**Prose, titles and filenames keep the special letters. Tags use an ASCII
slug.** The substitutions are `æ` → `ae` and `ō` → `o`.

| Name | Tag |
|---|---|
| Elværi | `#elvaeri` |
| Luminæri | `#luminaeri` |
| Vatæri | `#vataeri` |
| Drakōri | `#drakori` |

This holds for derived tags too: a tag built from one of these names carries the
slug, so the god of the Elværi is `#elvaeri-lady`, not `#elværi-lady`.

**A new coined term with a special letter gets its slug decided when the term is
coined**, in the same step as its glossary entry (0007). A slug invented later by
whoever needs a tag first is how a second spelling enters.

## Consequences

**One violation exists in the vault, and it is a matched pair.** Measured
2026-08-06:

- `04 Characters/Götter/Elværi-Göttin.md:9` — `*Tag:* #elvaeri-lady` ✅
- `04 Characters/Götter/Luminæri-Göttin.md:9` — `*Tag:* #luminæri-lady` ❌

Two sibling notes, written to the same pattern, disagreeing on the rule. Nothing
in this repository catches that; it took counting tags to see it.

**Tag and name no longer look alike.** Someone reading `#elvaeri` and looking for
`Elvaeri` finds nothing, because the note is `Elværi`. That cost is real and is
accepted: the tag is for filtering, the name is for reading.

**The rule is unenforced.** The method's checker reads Markdown references and
spelling; it knows nothing about Obsidian tags. Obsidian will happily accept a
tag containing `æ` and show it as a separate tag next to the ASCII one, which is
precisely the failure mode — two entries in the tag pane, neither obviously
wrong.

## Alternatives considered

**Keep the special letters in tags.** Rejected: not typeable on the keyboards
this project is written on, and in practice it produces two spellings for one
concept — which is not a hypothesis, it is what happened to `#luminæri-lady`.

**Strip the special letters everywhere, including prose and filenames.**
Rejected outright. The letters are canon content; `æ` and `ō` mark esteem, and
removing them removes a distinction the language is built on.

**An alias so both spellings resolve to one tag.** Rejected because it does not
exist: Obsidian offers aliases for notes, not for tags. There is nothing to
configure.

**Slug everything, so every tag is derived mechanically from its name.**
Rejected as a bigger rule than the problem. Only four names carry special
letters. A general transliteration rule would also have to decide `ü` → `ue`
versus `u` for every German word in a tag, and the vault does not need that
answered.
