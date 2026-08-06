---
tags:
  - meta
---
# 0007: Glossary upkeep alongside every new coined term

**Status:** Accepted · Decided 2026-06-23, recorded 2026-08-06

## Context

`Glossar.md` is the one place where a term can be looked up without knowing which
note defines it. It holds a German and an English section, each entry linking to
the note the term comes from.

A glossary decays in one direction only. Terms are invented while writing a note,
in the flow of that note, and the glossary is somewhere else. Nothing about
writing the note reminds anyone. So the glossary drifts behind the vault, and the
gap is invisible from both sides: the note looks complete, and the glossary looks
like a glossary.

Once it has drifted far enough, its silence stops meaning anything. A term that
is not in it might be new, or might be missing, and the only way to tell is to
search the vault — which is what the glossary existed to avoid.

## Decision

**A new coined term gets its glossary entry in the same work step as the note
section that introduces it.** Not afterwards, not in a cleanup pass.

The entry goes in **both** sections, German and English, alphabetically, linking
to the source note in the form `[[Note#Heading|Display]] → kurze Definition`,
with a short factual definition in each language.

**What earns an entry** is what earns an `*EN:*` gloss under 0003, plus named
entities: Eigenbegriffe, named persons, places, historical events and references,
organizations, artifacts. **Generic headings do not** — *Geschichte*,
*Gesellschaft*, *Biologie* — mirroring 0003 exactly, so that one judgment covers
both rules.

**Renaming or deleting a term updates or removes its entry in the same step.** A
glossary entry pointing at a heading that no longer exists is worse than a
missing one: it is a wrong answer given confidently.

`Glossar.md` is edited under 0006 like any vault file — Python, UTF-8,
verification in the same block. It is long, it is dense with `[[wiki-links]]`, and
it is exactly the kind of file naive editing truncates.

## Consequences

**The rule doubles the cost of coining a term, and that is the point.** Two
entries plus a definition in each language is enough work to make a session think
about whether the term is worth having. Terms that do not survive that question
should not be in the vault.

**Every glossary entry is a reference that can rot.** As of 2026-08-06 the file
holds 176 `[[wiki-links]]` and no ordinary Markdown links, which means the
method's reference check reads **none** of them. If a heading is renamed while
Obsidian is closed, the entry breaks and nothing anywhere reports it. This rule
has no automated backstop at all.

**It depends on a rule being followed at the least convenient moment.** The step
where it applies is the step where the writer's attention is on the world, not on
bookkeeping. That is why it is written into `CLAUDE.md` as part of the work step
rather than as a maintenance task — a maintenance task is a thing nobody
schedules.

**The obligation is not one-way.** 0003 says which headings get an `*EN:*` line;
this record says those same terms get glossary entries. Applying one without the
other leaves the vault in the state this rule exists to prevent, with the term
defined in one place and findable from neither.

## Alternatives considered

**A periodic glossary sweep.** Rejected: a sweep is a task with no trigger, and a
task with no trigger does not happen. It also finds the missing terms long after
the context that produced them is gone, so the definitions get reconstructed
rather than recorded.

**Generate the glossary from the `*EN:*` glosses.** Attractive and rejected as
currently impossible: the gloss carries the English name and no definition, and
the definition is most of an entry's value. It would also need a reliable way to
find every gloss — which is a script this project does not have, and would have
to maintain.

**Only a German glossary; translate at the end.** Rejected for the reason 0003
gives: an English form settled at translation time is settled by whoever
translates, without the reasoning that produced the term.

**Let the glossary be partial and say so.** Rejected: a glossary that admits it is
incomplete answers nothing. The whole value of looking a term up is that absence
means something.
