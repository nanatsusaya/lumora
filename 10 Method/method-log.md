---
tags:
  - meta
---
# Method log

A running record of **how** we work here and why it looks like this - separate
from [[ADR]], which records what was decided about the work, and from [[STATUS]],
which records where the work stands.

This exists because the project is maintained across many sessions, and an agent
picking up work has this repository and nothing else: no conversation history,
no memory of how a rule came to exist. A rule whose origin is lost gets quietly
dropped by the next session that finds it inconvenient, and dropped in good
faith, because from the outside an unexplained rule is indistinguishable from an
arbitrary one.

**What goes here:** a correction and the reasoning behind it, a workflow
experiment and its outcome, a mistake worth not repeating.

**What does not:** routine task execution. That is what the commit history and
[[STATUS]] are for.

**The test before writing an entry:** *would an agent with no memory of that
session decide worse without this?* If not, leave it out. An entry per session
turns the log into a diary, and a diary is not read.

## Entry format

```
## YYYY-MM-DD - Short title

**Trigger:** how the topic came up.
**Action:** what was actually done.
**Impact:** what changed as a result - or did not.
**Lesson:** what this suggests for next time, if anything.
```

Quote a person verbatim and in their own language when the wording is the point.
A translated quotation is a paraphrase wearing quotation marks, and the reader
cannot tell.

---

## 2026-08-06 - American spelling, and why nothing is excluded from the scans

**Trigger:** the adoption had to declare one spelling regime. The neighboring
project `DasSchwarzeAuge/dsa5` declared British and then had to exclude eleven
directories from the scans to keep the run clean, and its own method log records
what that cost: its decision records sat in the exclusion list for weeks, and
nothing reported that their references were rotting, because nothing looked at
them. Daniel's instruction was blunt: *"der englische text soll im amerkanischen
sein, kein britisch englisch! entsprechend die rechtschreibung"*.

**Action:** both regimes were measured against all 144 files before anything was
written.

| Regime | findings, total | in the German corpus | in the English documents |
|---|---|---|---|
| british | 24 | 20 | 4 |
| american | 12 | 4 | 8 |

**Impact:** American more than halves the findings, and the reason is mechanical
rather than stylistic. The general `-ise` preference runs **only** under a
British regime, and the word scanner breaks words at `[A-Za-z]`, so a German
umlaut splits a word and leaves an English-looking fragment: *Nährungsreize*
becomes `hrungsreize`, and the `-ize` rule fires on it. The same happened to
*Brechungsindizes*, *Novize*, *Ehrgeizes*. All of those disappear under
American. What is left in the whole German corpus is four findings, all the
single word *Analyse*. That is not worth taking 141 documents out of every scan
for, so `ignore` is empty and `language.allow` holds two words instead. The
checker names every exempted word in every report; a list of two is readable, a
list of eleven directories is not.

Counter-testing the exemption — taking `Analyse` out of `language.allow` and
confirming the findings come back — produced **five**, not four. The fifth is the
paragraph above: an entry that names the word it exempts is itself scanned. It
is left standing, because an entry that cannot say which word it is about
explains nothing, and it is written down here so that a later count of five is
not read as drift. This paragraph writes the word in a code span instead, which
the checker never scans — its own advice, and the reason the count is five and
not six.

**Lesson:** measure the exclusion before writing it. The neighboring project's
list looked like housekeeping and was in fact a hole in the link check. An
exemption that names a word can be audited; one that names a directory cannot.

## 2026-08-06 - Artifacts in English, procedures in German

**Trigger:** the method wants one language per project. This project has two by
design: the novel is German, and its notes are the author's working material.

**Action:** the line was drawn by *what the file steers*, not by where it sits.
`CLAUDE.md`, `README.md`, `.github/` and everything in `10 Method` are English,
because they carry the method and are read against an English rule catalog. The
vault, including the prose in `08 Writing`, stays German. The five session
procedures under `.claude/skills/` are German too - they are read during work,
next to the German notes they act on, and a procedure in the wrong language gets
skimmed. This is written down as an L1 adaptation of kind `narrowed`, which
leaves the automated check running.

**Impact:** the spelling scan still runs over every file. What is narrowed is
what a clean run *means*: over German prose the scan compares against English
word pairs it never meets, so silence there is silence, not a result.

**Lesson:** an adaptation that switches a check off buys nothing here. `narrowed`
keeps the check and states its reach, which is the honest form when a rule
half-applies.

## 2026-08-06 - Why `10 Method` and not `09 Meta`

**Trigger:** `09 Meta` already exists and already describes the vault, so it
looked like the obvious home for the four artifacts.

**Action:** it was not used. `09 Meta` answers *what is this project* - founding
document, elevator premise, genre stance, the tag glossary. It is written for a
reader who wants to understand Lumora. The method artifacts answer *how is work
done here*, and they are written for whoever does the next piece of work. Mixing
them would have put a status that changes weekly next to essays that have not
changed in months.

**Impact:** a new top-level folder, `10 Method`, with its own overview note
named after it, following the vault's existing convention.

**Lesson:** the test for where an artifact goes is which question it answers,
not which folder is closest in name.

## 2026-08-06 - `main` stays unprotected, and the commit rule became situational

**Trigger:** the method's G1 wants a human gate between a change and the trunk,
and its automated part is a hosting-platform setting. Lumora has none: no branch
protection, no ruleset, and 0 pull requests in 198 commits. Asked directly,
Daniel was explicit twice: *"ich will kein branch schutz auf dem main"* and
*"nein kein schutz auf dem main"*.

**Action:** recorded as a G1 adaptation of kind `narrowed`, with the reason and
the date, and `authorities.gate` set to `null`. A pointer to a settings page
where nothing is configured would assert a boundary that does not exist.

The second half is a collision this adoption found: `CLAUDE.md` said *"Daniel
handles all git commits. Claude never runs `git commit`"*, while the method
requires the agent to branch, commit and open a pull request. Daniel resolved
it: *"die regel das ich commite weichen wir auf. das wird situationsabhängig"*.
The rule now reads: an agent may commit on a branch and open a pull request;
`main` and merging stay with Daniel.

**Impact:** the gate exists as a way of working, not as a setting. A push
straight to `main` is technically possible and nothing prevents it, not even by
accident. That is stated in the adaptation rather than hidden, so that a later
session reading a green check does not conclude the trunk is guarded.

**Lesson:** when a rule cannot be enforced, write down what is therefore not
guaranteed. A check that passes because nothing was checked is the failure mode
worth naming.
