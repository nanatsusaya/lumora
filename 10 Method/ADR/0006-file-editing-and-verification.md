---
tags:
  - meta
---
# 0006: File editing through Python, and verification in the same step

**Status:** Accepted · Decided 2026-08-06 (recording a practice in force since
the vault was created)

## Context

Almost every file in this vault contains characters that break naive text
editing: German umlauts, `ß`, em-dashes, `æ` and `ō` in species names, and
Obsidian `[[wiki-links]]` in 1,892 places. Editing tools that assume one byte per
character, or that stream a file through a shell, **truncate** such files — and
the truncation is silent. Nothing errors. The file is simply shorter than it was.

This is not a hypothesis. `README.md` sat on `main` ending in
`© 2026 Daniel Wag`, with no trailing newline, for long enough that nobody knows
when it happened; the English half of the same file says *Daniel Wagner*. It was
found on 2026-08-06 by reading the file to its end, and only then.

The second failure mode is quieter still. When Python writes to a file Obsidian
is holding open, the result can contain **null bytes** — the content looks right
in a terminal and the file is corrupt.

The third is the failed replacement. `str.replace()` that matches nothing returns
the string unchanged and raises nothing. A script that writes the result reports
success and has changed no file.

## Decision

**Never use the `Edit` tool or `sed` on vault markdown.** Both truncate files
containing the characters this vault is made of.

**Always use Python with explicit UTF-8 encoding**, for reading as well as
writing:

```python
with open(path, 'r', encoding='utf-8') as f:
    content = f.read()
# change content in memory
with open(path, 'w', encoding='utf-8') as f:
    f.write(content)
```

New content written as a Python string literal starts **without a leading
newline**, or uses `textwrap.dedent`. A leading newline puts a blank line above
the frontmatter, and Obsidian then does not read the frontmatter at all.

**The verification runs in the same code block as the write.** A write block
without it is unfinished — not written and then checked, but a single step that
is not complete until it has checked itself. A separate follow-up step is a step
that gets skipped when the first one appears to have worked.

Five checks, every time:

1. **Read the file back completely.** `cat` or the `Read` tool — **never**
   `tail`. Only a full read shows that nothing was cut off, and the truncation
   above is exactly what a `tail` confirms as fine.
2. **Count null bytes:** `content.count(chr(0)) == 0`. If any are found, cut
   everything from the first one, verify the remainder ends correctly, write
   again.
3. **Confirm every `str.replace()` matched.** If the pattern was not found, stop
   and report. Never continue past a failed replacement.
4. **Check the content is complete** — no sentence cut off, no section missing,
   no unexpected end.
5. **Check nothing was duplicated** or overwritten with content from another
   file.

**If anything looks wrong: stop and report before doing anything else.**

On this machine the interpreter is `py` or `python`. There is no `python3`.

## Consequences

**Editing is slower, and deliberately so.** A one-word change costs a script with
a read, a replacement, a write and a verification. The alternative costs a file.

**The rule protects content that has no other backstop.** The method's checker
reads references and spelling; it would not notice a note losing its last three
paragraphs. Git would — in a diff nobody reads before committing.

**Check 3 is the one that fails silently in the other direction.** A script whose
pattern does not match writes a file identical to the one it read, and every
other check passes. Only asserting the match distinguishes "changed nothing
because nothing needed changing" from "changed nothing because the pattern was
wrong".

**Null bytes come from Obsidian being open.** Closing the vault before a scripted
edit avoids them; check 2 exists because nobody remembers to.

**Nothing enforces any of this.** It is a rule about how work is done, not a
property of the repository, and an agent that ignores it produces a clean-looking
diff of a damaged file.

## Alternatives considered

**Use the ordinary editing tools and rely on review.** Rejected on the evidence.
The `README.md` truncation survived every review it passed through, because a
truncation looks like a file that simply ends.

**Verify in a separate step after writing.** Rejected: it is the step that gets
dropped when the write appears to have worked, which is precisely when a silent
truncation is invisible.

**Ban scripted editing and require Obsidian.** Rejected: this vault is worked by
agents, and an agent cannot open Obsidian. It would ban the work, not the risk.

**A pre-commit hook checking for null bytes and truncation.** Not rejected —
untried. Null bytes are mechanically detectable and would be a genuine check
rather than a rule. Truncation is not, since nothing knows how long a file should
be. Worth its own ticket; it would narrow this record, not replace it.
