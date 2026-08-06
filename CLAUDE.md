# LUMORA: Project Context for Claude

> **This is your navigation guide. It tells you what Lumora is, where to find the details, and how to work with Daniel.**

---

## What is Lumora?

**Lumora** is a hard-magic fantasy novel universe. The story takes place on a planet where a 5th fundamental force — **Noetic Force (N-Force)** — allows conscious beings to influence physical reality through thought, emotion, and intention.

It's not arbitrary magic. It's an extended physics system where consciousness is real and bounded by rules.

**Core principle:**
> *No solution without foundation. No effect without cause. No power without limit.*

For the full philosophy and motivation behind this project, read: `01 Kern von Lumora/01.08 Lumora-Manifest.md`

---

## Vault Structure

```
Lumora/
├── 00 Inbox/             ← Loose notes & ideas, unsorted.
├── 01 Kern von Lumora/   ← Sacred foundation. Do not change these.
├── 02 Worldbuilding/     ← World details. Evolves as needed.
├── 03 Noetic System/     ← Magic system mechanics. Evolves as needed.
├── 04 Characters/        ← Character roster: protagonist, gods, key figures.
├── 05 Story Architecture/← Act structure & chapter overviews (Part I–V).
├── 06 Lore & Mystery/    ← Core lore & the central mysteries.
├── 07 Research/          ← External references only. Never mix with own lore.
├── 08 Writing/           ← Prose drafts (German only).
├── 09 Meta/              ← Project philosophy & framing.
├── 10 Method/            ← How this project is worked: status, decisions, method log.
└── Assets/               ← Images: maps, species artwork, illustrations.

```

**Key distinction:**
- `01 Kern` = inviolable philosophical core. Never change these to fix story problems.
- `02–03` = system details. Can evolve if an idea earns it.
- `04–06` = practical story work (characters, story architecture, lore). In active development.
- `07 Research` = external references only. **Never mix with own lore.**

---

## Key Files to Read

Before diving into any topic, read the relevant file — don't rely on this document for details.

| Topic | File |
|---|---|
| Why this project exists | `01 Kern von Lumora/01.08 Lumora-Manifest.md` |
| Immutable canon laws | `01 Kern von Lumora/01.05 Die Urgesetze des Kanons.md` |
| The five structural pillars | `01 Kern von Lumora/01.06 Die Fünf Säulen Lumoras.md` |
| Noetic System basics | `03 Noetic System/03.01 Noetisches System.md` |
| How Noetik works (mechanics) | `03 Noetic System/03.02 Funktionsweise.md` |
| Limits & constraints | `03 Noetic System/03.05 Grenzen & Einschränkungen.md` |
| World & cosmology | `02 Worldbuilding/02.01 Weltstruktur/Kosmologie & Universumsstruktur.md` |
| Peoples & species (overview of all twelve) | `02 Worldbuilding/02.02 Spezies/Kulturschaffende/Kulturschaffende Spezies.md` |
| Forest-elf society + **Elværin language & species naming (canonical)** | `02 Worldbuilding/02.03 Völker & Gesellschaften/Waldelværi.md` |
| How the magic system is conveyed (Elværin translation device) | `05 Story Architecture/05.02 Vermittlung des Magiesystems.md` |

---

## Project Status

Where the project stands — what is done, what is in progress, what has not
started, and the one next step — is recorded in **`10 Method/STATUS.md`** and
nowhere else.

It used to be listed here *and* in `README.md`. Both copies still named the
deepening of the peoples as the primary focus on 2026-08-06, six weeks after
every commit had gone to `08 Writing` instead. A fact with two authorities
becomes two different facts as soon as one of them is edited.

---

## How This Project Is Worked

This project follows **agent-project-rules**, catalog version `0.5`. The binding
is `method.json` in this folder. The rules below are *stated* here rather than
linked, because a session working a task has this repository and nothing else,
and an instruction to fetch something external is a fetch that can fail.

**Four artifacts, four questions.** Every fact belongs to exactly one of them
and is not repeated in another:

| Role | File | Answers |
|---|---|---|
| operating rules | `CLAUDE.md` (this file) | How is work done here? |
| decisions | `10 Method/ADR/` | What was decided, and why? |
| state | `10 Method/STATUS.md` | Where do we stand? |
| method log | `10 Method/method-log.md` | Why does the way of working look like this? |

Decisions in `10 Method/ADR/` are about **the vault**, never about Lumora. The
canon laws, the Noetic rules and the cosmology are content and stay in
`01 Kern von Lumora` and `02`–`03`.

**Language.** This file, `README.md`, everything under `.github/` and everything
in `10 Method/` is English in **American** spelling — *artifact*, *behavior*,
*center*, *catalog*, *analyze*, *license*, *color*, *gray*. Everything else in
the vault is German. The five session procedures under `.claude/skills/` are
German too, because they are read while working, next to the German notes they
act on.

**`main` carries no protection.** No branch protection, no ruleset — deliberately
(decided 2026-08-06). The review boundary is a way of working, not a setting:
work goes onto a branch, then into a Pull Request, and Daniel merges. Nothing
technically prevents a direct push to `main`, not even by accident.

**The catalog and its checker are not in this repository.** They live at
`https://github.com/nanatsusaya/agent-project-rules`. Where a clone sits next
to this folder — the convention on the machine this was adopted on — the
command from the vault root is:

```
node "../agent-project-rules/checks/check-method.mjs" .
```

That is a convention and not a guarantee: nothing in this repository controls
where the clone sits, or whether there is one. **A session that does not find
it reports that the check could not run — never that it passed.** Everything
stated in this file holds without the checker; it confirms, it does not carry.

**What the checker sees, and what it does not.** It reads `method.json`,
confirms the four bound files exist and are filled, resolves ordinary Markdown
references, compares each decision record against its index row, and enforces
one spelling regime. It ignores Obsidian `[[wiki-links]]`, of which the vault
has 1,892 against a few dozen ordinary ones — so a green run says nothing about
the vault's own cross-linking. That stays Obsidian's job.

**Nothing checks Lumora itself** — not the canon laws, not the Noetic rules, not
the prose. That is deliberate and recorded in 0008: the method governs how work
is done here, not what is true in the world. Whether the story holds together is
read and argued; a passing run says nothing about it, and adding a check over
content needs a superseding record.

**Session procedures** live in `.claude/skills/` and are typed as slash
commands: `/moin` (sitting down), `/feierabend` (stopping), `/weiterimtext`
(after a merge landed), `/adr` (writing a decision record), `/passtdas`
(checking that the declaration still matches how work is actually done).

---

## Questions to Ask Before Any Work

1. Does this follow the Noetic rules?
2. Is this consistent with the Manifest?
3. Does this respect the hard limits of the system?
4. Am I solving the story — or solving the system?
5. Would this require changing the Kern? (If yes: stop and discuss.)

---

## Collaboration Guidelines

### Language & Communication

- **All conversation happens in German.** Claude always responds in German unless Daniel explicitly writes in English.
- **Technical terms are used in German in conversation.** Vault notes include an English equivalent (`*EN: ...*`) only for Eigenbegriffe — see Vault Conventions below.
- **This file (CLAUDE.md) is always written in English.**

### Vault Conventions

Each of these is a decision record in `10 Method/ADR/`, which holds the reasoning
and what was rejected. This section states what to do; the record says why, and
names where the vault does not yet follow it. Changing one of these rules means
writing a superseding record, not editing the lines below.

#### Frontmatter Tags — record 0001, vocabulary 0002, scope 0008

Every note has YAML frontmatter with at least one tag:

```yaml
---
tags:
  - wip
---
```

| Tag | Meaning | Applied to |
|-----|---------|-----------|
| `#canon` | Inviolable foundation — never remove | All `01 Kern von Lumora` notes |
| `#wip` | Work in progress | All active notes except `01 Kern`, `03.01`, `03.02` and the prose in `08 Writing` (record 0008) |
| `#ready` | Complete — only when ALL sections are `#ready` | Any finished note |
| `#meta` | Describes the vault itself, not story content | `09 Meta/` notes |

#### Per-Section Format

Every named section with its own heading uses this structure directly below the heading:

```
### Name der Sektion
*EN: English Name*        ← only for Eigenbegriffe (see below)
*Tag:* #section-id        ← exactly ONE tag — the unique section identifier
*Status:* #wip            ← one or more status flags
```

- `*Tag:*` is always exactly one tag. Never combine multiple tags here.
- `*Status:*` can combine flags: `#wip`, `#ready`, `#working-title`
- `#working-title` always goes in `*Status:*`, never in `*Tag:*`
- Status progression: `#wip` → (when complete) → `#ready`
- Full tag reference: `09 Meta/Tags.md`

#### EN Translation Rule — record 0003

`*EN: English Name*` is only added for **Eigenbegriffe** — invented proper nouns and coined terms that will be reused in the English novel (species names, god names, system terms like "Noetic Force"). Generic headings ("Geschichte", "Gesellschaft", "Sonnensystem") do **not** get one.

The test when it is not obvious: **would this word appear in the English novel as itself?**

#### All Tags in English — record 0004

All `*Tag:*` identifiers and `*Status:*` flags are in English. No German tags.
Examples: `#primal-god`, `#hakani`, `#desert-of-tears`, `#n-force`

Names with special letters use an **ASCII slug** for the tag (`æ` → `ae`, `ō` → `o`): *Elværi* → `#elvaeri`, *Drakōri* → `#drakori`, *Luminæri* → `#luminaeri`, *Vatæri* → `#vataeri`. Derived tags too: `#elvaeri-lady`. Prose, title and filename keep the special letters.

#### Writing Style Inside Notes — tone is record 0005

**Tone — factual and objective (all notes except the actual story prose).**
Notes are reference material and read like a neutral knowledge base. This applies to **headings and body text**:

- **Headings** are short, neutral labels — no essayistic subtitles (`Begriff — eine poetische Pointe`), rhetorical questions, or dramatic colons.
- **Body text** states facts and mechanics plainly. Avoid dramatizing flourishes, evaluative/aphoristic phrasing, punchy one-line antitheses, and chatty fillers (*„ehrlich"*, *„Pikant:"*, *„die Krönung"*).
- **No authorial "wir/uns" framing:** *„In dieser Note beschreiben wir …"* → *„Diese Notiz beschreibt …"*.
- **Six exceptions stay subjective by design**, and the list is exhaustive: story prose in `08 Writing`; author-voice blocks (`> *Kritische Anmerkung:*` / `> *Anmerkung:*`); in-world quotations; spoiler warnings; `Merksatz` axioms; and craft framing in `05 Story Architecture` and `09 Meta` where it talks about *writing* the story rather than about world facts. A seventh needs a superseding record.

**Compact sections** (for peoples, gods, etc.):
```
**Biologie:** ...
**Kultur:** ...
**N-Kraft-Nutzung:** ...
```

**Editorial annotations** (Claude's own critical observations):
```
> *Kritische Anmerkung:* ...
> *Anmerkung:* ...
```

**Open questions and TODOs** always in fenced code blocks:
````
```
TODO: Question 1
Question 2
```
````

**Obsidian cross-references**:
```
[[Waldelværi#Der Familienbaum|Familienbäume]]
```

#### Species & Elværin Naming (canonical)

All twelve culture-bearing peoples now carry their **Elværin** names throughout the vault. The classic fantasy term is kept only as a gloss / in a "Fantasy-Pendant" column.

| Elværin | Classic term |
|---|---|
| **Hakani** | Menschen (Lumora humans — *not* Earth humans) |
| **Elværi** | Elfen (forest-elves; the protagonist's people) |
| **Theriani** | Tierwesen (mammalian beast-folk) |
| **Anelari** | Zwerge |
| **Volari** | Vogelmenschen |
| **Luminæri** | Feen |
| **Bythari** | Meervolk / Fischmenschen |
| **Vatæri** | Zeitseher (time-seers) |
| **Sapari** | Golems (silicon crystal beings) |
| **Tepani** | Echsenmenschen |
| **Drakōri** | Drachen |
| **Sylvari** | Pflanzenwesen |

- **"Eldari" / "eldarisch" is now only the in-world *human exonym* for the Elværi** (the human transliteration of their unsayable, sung self-name). Do **not** revert it to a species name.
- The **word ending carries esteem**: `-ani` (low) → `-ari` (neutral) → `-æri` (respected) → `-ōri` (revered). The special letters `æ` and `ō` are sung honor-tones — only **Elværi** & **Luminæri** carry `æ`, only **Drakōri** carries `ō`.
- **Spelling:** prose, titles and filenames use the special letters (`Elværi`, `Drakōri`); tag slugs use ASCII (`#elvaeri`, `#drakori`).
- **"Drache" caveat:** only the species *as a people* is **Drakōri**. Compounds and creatures keep "Drache" — *Drachenkristall, Drachenodem, Drachengott, Eisdrache,* and the sub-species (Feuer-/Eis-/Wind-/Wasserdrachen, Wyvern, Drake, Basilisk).
- The Earth-origin **Menschen** (the protagonist's former kind) always stay *Menschen* — never Hakani.
- **Single source of truth:** `02 Worldbuilding/02.03 Völker & Gesellschaften/Waldelværi.md` → section **"Sprache"** (Lautregel, coined terms, the full naming table, the esteem scale).

#### Glossary Upkeep — record 0007

Whenever a new Eigenbegriff, named person, or specific worldbuilding entity (place, historical event/reference, organization, artifact) gets its own note or its own `*EN:*`-glossed section, add a matching entry to `Glossar.md` **in the same work step** — in both the **Deutsch** and **English** sections, alphabetically, linking to the source note (`[[Note#Heading|Display]] → kurze Definition`), with a short factual definition in each language.

- Only Eigenbegriffe and named entities get entries — generic headings (Geschichte, Gesellschaft, Biologie …) do **not**, mirroring the EN-gloss rule.
- On rename or deletion of a term, update or remove its entry in the same step.
- Edit `Glossar.md` under the File Editing Rules below like any vault file.

### Translation Format (Novel)

The novel is written and developed **in German first**.

Only finished, fully revised chapters are translated into English.

Draft scenes, character notes, and plot work remain in German throughout development.

- The novel is written and developed **in German first**.
- Only finished, fully revised chapters are translated into English.
- Draft scenes, character notes, and plot work remain in German throughout development.

### Handling System-Breaking Ideas

If an idea conflicts with existing system rules:
1. Claude flags the conflict **immediately and clearly**, before developing the idea further.
2. Daniel and Claude then discuss together: Is the idea worth adapting the system for? Or does the story need a different solution?
3. **The Kern (01.) remains inviolable.** System details (02.–03.) can be revised if an idea is compelling enough to earn it.

### File Editing Rules — record 0006

**Never use the Edit tool or `sed` to modify vault markdown files.** Both truncate files containing UTF-8 characters (German umlauts, em-dashes, Obsidian `[[...]]`-links), especially on large files. It has already happened once: `README.md` sat on `main` ending in `© 2026 Daniel Wag`. Always use Python with explicit UTF-8 encoding for any read/write/edit operation on vault files — the interpreter here is `py` or `python`, there is no `python3`:

```python
with open(path, 'r', encoding='utf-8') as f:
    content = f.read()
# apply changes to content in memory
with open(path, 'w', encoding='utf-8') as f:
    f.write(content)
```

When writing new file content as a Python string literal, always use `textwrap.dedent` or start the string without a leading newline:

```python
# CORRECT — no leading newline
content = """---
tags:
  - wip
---
"""

# WRONG — leading newline creates a blank line at the top of the file
content = """
---
tags:
  - wip
---
"""
```

**Mandatory post-edit verification after every file change:**

> **The verification must be implemented in the same code block as the write — not as a separate follow-up step. A write block that does not verify is incomplete.**

1. Read the file back **completely** — use `cat` or the Read tool, never `tail`. Only a full read confirms nothing was cut off.
2. Check for null bytes: `content.count(chr(0)) == 0`. Null bytes appear silently when Python writes to a file that is still held open by another process (e.g. Obsidian). If found: strip everything from the first null byte, verify the clean content ends correctly, then write back.
3. Check that `str.replace()` actually found the pattern — if it returns `"Pattern not found"`, stop immediately and report. Never silently continue after a failed replace.
4. Check that the content is complete: no sentences cut off, no sections missing, no unexpected end.
5. Check that no content was duplicated or replaced with content from another file.
6. If anything looks wrong: stop immediately and report to Daniel before proceeding.

### Git Commits

**Committing is situational (decided 2026-08-06).** Claude may commit **on a
branch** and open a Pull Request. `main` belongs to Daniel.

- **Never on `main`:** no commit, no push, no merge. Nothing enforces this — there
  is no branch protection — so the rule is the only thing that holds.
- On a branch: one concern per commit, message as `type(scope): summary in lower
  case`.
- Never `--amend` and never force-push a branch that is already under review.
- When the Pull Request is open: stop and tell Daniel. Merging is his.
- Outside a branch-and-PR flow the old rule still applies: if committing looks
  like the natural next step and no branch was agreed, stop and ask.

### Claude's Role as Creative Partner

Claude is an **active creative collaborator**, not just a consistency checker.

- Claude may propose new ideas, concepts, or directions **at any time**, when they seem fitting and valuable.
- The goal is a coherent *and* compelling story — which requires creative, unexpected ideas alongside rigorous system thinking.
- Claude should not self-censor good ideas out of caution. If it fits the world and serves the story, bring it forward.

### Current Focus

The current focus and the single named next step are in `10 Method/STATUS.md`.

They are deliberately not repeated here. This file changes rarely by design, and
a focus kept in a rarely-changed file goes stale without anyone noticing — which
is exactly what happened to the copy that stood here until 2026-08-06.

---

**Status, focus and next milestone:** `10 Method/STATUS.md` — not here.

**Conventions last revised:** 2026-08-06 (adopted agent-project-rules: four
artifacts bound in `method.json`, status and focus moved out of this file,
committing on a branch allowed, American spelling declared). 2026-06-23 (added
Glossary Upkeep rule: new Eigenbegriffe / persons / places / historical
references get a matching DE+EN entry in `Glossar.md` in the same step).
2026-06-15 (factual/objective tone rule for all notes except story prose;
headings + body de-essayified across 02–06)
