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
├── 01 Kern von Lumora/   ← Sacred foundation. Do not change these.
├── 02 Worldbuilding/     ← World details. Evolves as needed.
├── 03 Noetic System/     ← Magic system mechanics. Evolves as needed.
├── 04 Characters/        ← Not yet developed.
├── 05 Story Architecture/← Not yet developed.
├── 06 Lore & Mystery/    ← Not yet developed.
├── 08 Writing/           ← Prose drafts (German only).
└── 09 Meta/              ← Project philosophy & framing.
```

**Key distinction:**
- `01 Kern` = inviolable philosophical core. Never change these to fix story problems.
- `02–03` = system details. Can evolve if an idea earns it.
- `04–08` = practical story work. Flexible, mostly not yet started.

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
| Limits & constraints | `03 Noetic System/03.04 Grenzen & Einschränkungen.md` |
| World & cosmology | `02 Worldbuilding/02.01 Weltstruktur/02.01 Kosmologie & Universumsstruktur.md` |
| Peoples & species | `02 Worldbuilding/02.02 Völker & Spezies/02.02 Völker & Spezies.md` |

---

## Project Status

### Done ✅
- Core philosophy & canon foundation (`01 Kern`)
- Noetic System fundamentals (basics, functionality, limits)
- Cosmology & world structure basics

### In Progress 🔄
- Noetic System details (cellular biology, advanced applications)
- Worldbuilding depth (peoples, regions, societies, religion)

### Not Yet Started 📋
- Characters, plot structure, scenes, timeline

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

#### Frontmatter Tags

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
| `#wip` | Work in progress | All active notes except `01 Kern`, `03.01`, `03.02` |
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

#### EN Translation Rule

`*EN: English Name*` is only added for **Eigenbegriffe** — invented proper nouns and coined terms that will be reused in the English novel (e.g. species names, god names, system terms like "Noetic Force").

Generic headings (e.g. "Geschichte", "Gesellschaft", "Sonnensystem") do **not** get an EN line.

#### All Tags in English

All `*Tag:*` identifiers and `*Status:*` flags are in English. No German tags.
Examples: `#primal-god`, `#humans`, `#desert-of-tears`, `#n-force`

#### Writing Style Inside Notes

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
[[02.02 Völker & Spezies#Golethari|Golethari]]
```

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

### File Editing Rules

**Never use the Edit tool or `sed` to modify vault markdown files.** Both truncate files containing UTF-8 characters (German umlauts, em-dashes, Obsidian `[[...]]`-links), especially on large files. Always use Python with explicit UTF-8 encoding for any read/write/edit operation on vault files:

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
1. Read the file back and check the relevant section is complete and correct.
2. Check that no content was cut off, duplicated, or replaced with content from another file.
3. If anything looks wrong: stop immediately and report to Daniel before proceeding.

After any bulk file operation, always verify file endings with Python's `glob` + `tail` check before committing.

### Git Commits

**Daniel handles all git commits. Claude never runs `git commit`** (or any variant like `--amend`, `-am`, etc.).

- Claude may stage files (`git add`) only if explicitly asked.
- When a task is complete and committing would be the natural next step: stop and tell Daniel.

### Claude's Role as Creative Partner

Claude is an **active creative collaborator**, not just a consistency checker.

- Claude may propose new ideas, concepts, or directions **at any time**, when they seem fitting and valuable.
- The goal is a coherent *and* compelling story — which requires creative, unexpected ideas alongside rigorous system thinking.
- Claude should not self-censor good ideas out of caution. If it fits the world and serves the story, bring it forward.

### Current Focus

- **Primary:** Noetic System — folder `03 Noetic System/`
- **Secondary:** Worldbuilding — folder `02 Worldbuilding/`
- Character work and story architecture come after the system and world are solid.

---

**Last updated:** 2026-05-28
**Project stage:** Worldbuilding & System Definition
**Next milestone:** Fill Noetic System details + expand Worldbuilding
**Conventions last revised:** 2026-05-28 (added vault tag system, section format, writing style)
