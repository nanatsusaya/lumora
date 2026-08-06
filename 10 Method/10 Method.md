---
tags:
  - meta
---
# 10 Method

This folder holds how the project is worked on. It says nothing about Lumora
itself: no worldbuilding, no lore, no characters, no story. Those live in `01`
to `08`. `09 Meta` explains the project to a reader; `10 Method` steers the
work of the people and agents doing it.

The project follows **agent-project-rules**, a rule catalog checked out at
`E:\My Projects\agent-project-rules`. Adopting it means binding four roles to
four real files. The binding itself is `method.json` in the vault root.

## The four roles

| Role | File | Answers | Changes |
|---|---|---|---|
| operating rules | `CLAUDE.md` | How do we work here? | rarely |
| decisions | [[ADR]] | What was decided, and why? | append-only |
| state | [[STATUS]] | Where do we stand? | often |
| method log | [[method-log]] | Why does the way of working look like this? | occasionally |

Each answers exactly one question. A fact belongs to one of them and is not
repeated in another, because two copies of a fact become two different facts as
soon as one is edited. Before the adoption on 2026-08-06 both `CLAUDE.md` and
`README.md` carried a Project Status, and both had been wrong for six weeks.

## Language

These files, `CLAUDE.md`, `README.md` and everything under `.github/` are
English, in **American** spelling. Everything else in the vault is German,
because the novel is written in German first and the notes are its working
material.

The session procedures under `.claude/skills/` are German as well: they are read
during work, next to the German notes they act on.

## Checking

The declaration is checked by a script in the method repository, run from the
vault root:

```
node "../agent-project-rules/checks/check-method.mjs" .
```

It reads `method.json`, confirms the four bound files exist and are not empty,
resolves ordinary Markdown references, compares each decision record against the
index, and enforces one spelling regime. It does **not** resolve Obsidian
`[[wiki-links]]`. Measured on 2026-08-06 the vault held 1,892 of those against
51 ordinary references, so a clean run says nothing about the vault's own
cross-linking. That stays Obsidian's job.
