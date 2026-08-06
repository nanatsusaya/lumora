# Session procedures

Five procedures, one per directory. They are **adapted copies** of the
`agent-method` plugin, version `0.5.0`, taken on 2026-08-06 from
[agent-project-rules](https://github.com/nanatsusaya/agent-project-rules).

Copying rather than installing is what that repository recommends for anyone who
wants to change them, and it is what makes this project self-supporting: the
procedures are here, in the repository, whether or not anything is installed.

| Command | Was | When to reach for it |
|---|---|---|
| `/moin` | `session-start` | Sitting down. Reads `10 Method/STATUS.md` first, ends with a question, never an action. |
| `/weiterimtext` | `after-merge` | A change just landed. Keeps context, re-verifies the outside world. |
| `/feierabend` | `session-end` | Stopping. |
| `/adr` | `decision-record` | Writing a decision record and taking it through to `Accepted`. |
| `/passtdas` | `adopt` | Checking whether `method.json` still matches how work is actually done. |

**The names and the prose are German**, while the four bound artifacts are
English. A skill name is typed in conversation rather than read in a committed
document, and the prose of a procedure is read while working - next to the
German notes it acts on. This is written into `method.json` as the L1
adaptation, so that the state is a choice rather than an accident. The plugin's
English originals stay reachable under `agent-method:` if they are ever wanted
back.

This file stays English. It is not a procedure but the record of how these five
differ from an English upstream, and half of what it does is quote that
upstream.

## What was changed

Each of these exists for a reason this project ran into:

1. **`/moin` drops the fallback for a project without `method.json`.** There is
   one, and it binds all four roles. A fallback that cannot fire is a sentence a
   reader has to rule out. The role table is inlined instead, with the note that
   `method.json` still wins if the two disagree.
2. **All five name this vault's write rules.** No `Edit` tool, no `sed`, Python
   with `encoding='utf-8'`, and the read-back verification in the same code
   block. Those rules exist because both truncate files containing German
   umlauts and `[[wiki-links]]`, and this is a repository made almost entirely
   of such files. A procedure that does not say so invites the one mistake that
   silently destroys content.
3. **Three procedures say that `main` carries no protection.** The method's G1
   assumes a configured gate; here there is none, deliberately. Where the
   original says "never write to the trunk" as if something enforced it, these
   say that nothing does.
4. **`/feierabend` states no definition of done of its own.** Two documents
   already carry it: the ticket, via
   [`.github/ISSUE_TEMPLATE/task.md`](../../.github/ISSUE_TEMPLATE/task.md), and
   the write rules in [`CLAUDE.md`](../../CLAUDE.md). A third copy would be a
   third authority. What it does add is this project's own bar: every written
   file is read back in full.
5. **`/feierabend` and `/passtdas` run the checker as its own command**, with
   the reason stated: a pipeline reports the last command's exit status, so
   trimming a check's output hides its failure.
6. **`/adr` no longer defines the shape of a record.** It points at
   `10 Method/ADR/ADR.md`, which is the only authority for the four-part body
   and the status vocabulary. Two descriptions of one form do not stay in
   agreement.
7. **`/adr` says what does not belong in a record.** The canon laws, the Noetic
   rules and the cosmology are content, not method, and the boundary is given as
   a test rather than a list.
8. **`/passtdas` leads with the review case** and keeps the first-time path at
   the end. `method.json` exists, so the adoption path cannot happen here. It
   also names both adaptations and what each one hangs on, so a review knows
   what to re-measure rather than re-assert.
9. **The catalog is named by its URL, not by a path on one machine.** The
   upstream copies point at a checkout; the first draft of these copies pointed
   at `E:\My Projects\agent-project-rules`, which is dead the moment this
   repository is cloned anywhere else — including through the Cowork desktop
   bridge. These name `https://github.com/nanatsusaya/agent-project-rules` and
   state the sibling-clone layout as the convention it is. Each of them also
   says what to do when the checker is not there: report that the check could
   not run. A check that cannot start proves nothing, which is exactly the
   failure a copied command hides best.

Everything not listed above is a translation of the upstream text.

**What was *not* changed, though it was expected to be.** A neighboring project
adopting this method had to fix procedures that called `python3`, which does not
exist on this machine. Neither the plugin nor the catalog mentions Python at
all, so there was nothing to fix. The interpreter is named in these copies only
because *this vault's own* write rules use Python, and here it is `py` or
`python`.

## The cost

These are copies. When the plugin releases a new version they no longer match
it, and nothing will announce that.

**The trigger is a release of `agent-project-rules`.** Compare these five files
against the new version, take what applies, and leave what was adapted on
purpose. The nine changes above are the list of what not to overwrite.

Since the prose is German, that comparison is a reading and no longer a diff. A
tool can show that an English paragraph changed upstream; nothing can show that
the German paragraph standing in its place still says the same thing. That is
the price, and it was paid knowingly.

## What is still here in English

Anything that is an identifier did not move with the prose: rule IDs (`L1`,
`G1`, `C4`, `D2`), commands, paths, and the status words that get typed into a
record - `Proposed`, `Accepted`, `Superseded`, `Planned` - stay English inside
German sentences, because they are what gets written into the file.

The **rules these procedures carry out** are not in this repository. The catalog
that says what `L1`, `D2`, `S3` or `C5` mean lives in `agent-project-rules`,
while `method.json` names two of those IDs in its adaptations. The procedures
give the path; they cannot give the text.
