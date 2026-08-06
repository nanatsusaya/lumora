---
tags:
  - meta
---
# 0003: When a heading gets an `*EN:*` gloss

**Status:** Accepted · Decided 2026-08-06 (recording a practice in force since
the vault was created)

## Context

The novel is written in German first, and only finished, fully revised chapters
are translated. That leaves a gap of months or years between inventing a term
and needing its English form.

If the English form is settled at translation time, it is settled by whoever is
translating, working from the finished sentence and not from the reasoning that
produced the term. *Noetische Kraft* could become *noetic power*, *mental force*
or *thought-force*, each defensible, none the same word. And a term that appears
in forty notes has to become the same English word in all forty.

The `*EN:*` line settles it at the moment of invention, in the note where the
term is defined. The cost is a line per heading, and that cost is why it is not
applied to every heading: a line the reader learns to skip is a line that stops
being read where it matters.

## Decision

`*EN: English Name*` goes directly under the heading, above the `*Tag:*` line
(0001), and **only for Eigenbegriffe** — invented proper nouns and coined terms
that will appear in the English novel as themselves.

That covers species names, god names, place names, and system terms such as
*Noetische Kraft* → *Noetic Force* and *N-Kraft* → *N-Force*.

**Generic headings do not get one.** *Geschichte*, *Gesellschaft*, *Biologie*,
*Sonnensystem* are ordinary German words with ordinary English equivalents, and
glossing them teaches nothing.

The test, when it is not obvious: **would this word appear in the English novel
as itself?** If yes, it is an Eigenbegriff and needs the line. If an ordinary
English word would do the job, it does not.

Species names that are already Elværin — *Elværi*, *Drakōri*, *Hakani* — are the
same word in both languages. They are still Eigenbegriffe, and the record that
matters for them is the glossary entry (0007), not a gloss that repeats the
heading.

## Consequences

**Every gloss creates an obligation elsewhere.** A term that earns an `*EN:*`
line also earns an entry in `Glossar.md`, in both the German and the English
section, in the same work step. That is 0007, and it is the half of this rule
that is easiest to skip.

**A term glossed twice, differently, is a defect and nothing catches it.** The
gloss lives next to the heading; there is no index of glosses to compare against.
Only the glossary makes a second English form visible, which is another reason
0007 is not optional.

**The boundary is a judgment, not a rule a command could apply.** *Familienbaum*
is an ordinary word in general German and a specific institution among the
Waldelværi. Whether it is an Eigenbegriff depends on what the note means by it.
The test above is the best available; it does not remove the judgment.

**A missing gloss costs nothing today and everything at translation.** Nothing
fails, no check turns red, and the term simply reaches the translator undefined —
which is exactly the state this rule exists to prevent.

## Alternatives considered

**Gloss every heading.** Rejected as noise. A vault where every heading carries
an English line is one where the line is furniture, and the reader stops seeing
it — including on the headings where it carries a decision.

**No glosses; decide the English at translation time.** Rejected: that hands a
worldbuilding decision to whoever translates, at the moment they are least
equipped to make it, and guarantees the same term arrives in several forms.

**A single English-terms file and no glosses in the notes.** Rejected as the
*only* mechanism. That file exists — it is `Glossar.md` — but a reader working in
a note needs the term's English form where the term is defined, not one file
away. The two are complementary, which is why 0007 requires both.
