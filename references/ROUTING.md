# ROUTING — where anything goes

> **A procedure, not advice. Run it.** It lives in the skill, not in the owner's folder, because only an agent ever runs it; the root `CLAUDE.md` carries its short form.
> It exists because the failure that kills these systems is almost never bad content. It is good content filed where nobody will look for it, at a trust level it never earned.

**Before any of this: does it carry a decision, a task, or something the owner is waiting for?** Those go first, in the same turn: the decision to `DECISIONS.md`, in the words that decided it; anything that needs the owner to a card in `TASKS.md`. A document is filed; what is *inside* it that someone has to act on is captured.

## The four questions, in order

Never skip one, never reorder them. If a question cannot be answered and has no default below, **ask the owner**, and park the item in `inbox/` until they answer. Inferring here is how things get lost.

### Q1 · Which area owns this?

- Fits exactly one area → that area.
- Fits two → the one the owner would **look in**, not the one it is *about*. Cross-link from the other.
- Fits none → `inbox/` (created with its first item). **Never invent an area to hold one file.**

**Material never earns an area.** If the honest answer to "what is this?" is a *kind of file* (backups, exports, invoices, screenshots, scripts, receipts), then it is material, and it belongs inside an existing area or in `archive/`. An area is an **area of work** (a client, a project, a team, a process the owner runs), and only the owner names one. The pull to open an area is strongest exactly when nothing fits, which is exactly when it is wrong: what you have then is a pile with no home, and the answer to that is `inbox/`.

### Q2 · What kind of thing is it?

| `kind:` | The question it answers |
|---|---|
| **evidence** | something I found, was told, or measured |
| **decision** | something that was chosen, which now governs |
| **work** | something in progress right now |
| **proof** | something that happened, with a result |

**In an area this system created, this is a label in the file's header block, not a folder**: everything lands in `notes/`, flat. **In an area that arrived with its own `current/` · `needs-review/` · `completed/` tree, the folder is the label.** Same four words, one form per area, never both.

**The trap worth naming:** a decision that arrives inside a working document is still a decision. Extract it into `DECISIONS.md`, with the sentence that decided it and who decided, or in six months it is invisible and someone decides it again, differently.

### Q3 · How far is it trusted?

| `trust:` | Meaning |
|---|---|
| `current` | Approved, in force |
| `needs-review` | Might be right. **Never quoted as fact.** |
| `completed` | Finished. Evidence of the past, not an instruction for now |
| `superseded` | Replaced. Historical context only |

**Default is `needs-review`.** Promotion to `current` belongs to the owner alone. An agent never promotes trust by itself, because a draft quoted as settled is indistinguishable from a fact until it causes damage.

### Q4 · How sensitive is it?

Inherit the area's `sensitivity`. An item in `inbox/`, or in a new area the owner has not rated yet, is `private` until they say otherwise. If this particular item is more sensitive than its area (a salary, a complaint about a colleague, a client's contract), say so and ask. Never file it quietly and hope.

---

## Keep the source, and link it

**When you extract, keep what you extracted from.** A summary whose source is gone cannot be checked, and the rulebook asks you to check the source rather than the summary. So the extraction names its origin in its first lines, and if the origin is a file it stays alongside. If the origin is a conversation, a meeting or a page, say so and give enough for someone to find it again.

**Link to what you would actually open.** Link a note to the decision it supports, the card it feeds, the source it came from. **Do not link every term that happens to match**; a graph where everything connects to everything says nothing at all.

## Filing is not finished when the file exists

Every one of these, every time:

1. The file, with `kind:` and `trust:` **in the header block, directly under the title, above any content**, and for anything factual, **the date it was true**.
   **Inside the file, every claim carries `evidence:` · `inferred:` · `unknown:`**, and an `evidence:` claim names where it came from. Per claim, not per file.
2. **A row in the area's `INDEX.md`** (created once the area passes about five files), under a topic heading in the owner's words.
3. **The area's `STATE.md`**: at minimum, the last-touched date.
4. **The `BOARD.md` row.**
5. A decision inside it → **a line in `DECISIONS.md`.**
6. Something only the owner can settle → **a card in `TASKS.md`**, with a recommendation and a default.
7. **One line in chat saying where it went.** The owner should never have to ask.

**Steps 2 and 3 are the ones that actually get skipped**, and skipping them is the whole failure: the file exists, it is invisible, and the person now believes the thing is handled.

## Hard limits

- **Never create an empty folder.** It appears with its first file.
- **Three levels below an area, for structure this system creates.** An imported area's own tree is exempt, however deep it runs.
- **About seven items per view**, excluding tool files. Past that, people stop scanning and start missing things.
- **A sub-folder appears from about the fifth row under its topic heading in `INDEX.md`.** One file does not get a house, and the count is **rows in the index, never a scan of the folder**, because no session reads a whole area. A new topic is a **heading** from the day it is declared; the folder follows the material.
- **No number prefixes on folder names.** `05-marketing` only holds up in a tree built in one sitting. These folders are born in the order work happens, and the numbers start lying within a month. The name is the topic, in the owner's words, identical to the index heading, and **the same word in every area** that has that topic.
- **No absolute paths. Anywhere.**

## Taking in an entire existing folder

### First: is any of it content at all?

A working directory is not a body of knowledge, and importing one wholesale turns a second brain into a junk drawer within a week. Four piles:

| Pile | Examples | What happens |
|---|---|---|
| **Never enters** | `.env`, key files, tokens, credentials, anything with a live secret in it | **Stays where it is. Not copied, not read beyond confirming what it is, not quoted.** Say it was left and why |
| **Not content** | `node_modules/`, `dist/`, `build/`, caches, lock files, `.tmp` | Skipped, and the skipping stated. A machine generated these and a machine can regenerate them |
| **Code and live projects** | anything with its own `.git`, anything being actively worked on | Pointer area, below. Never contained |
| **Actually knowledge** | notes, decisions, specs, research, documents, spreadsheets someone maintains by hand | This is what comes in |

**Say what landed in each pile.** The owner may disagree about one of them, and silent triage is indistinguishable from missing something. **If the fourth pile is small, say so plainly**: "most of this is a development environment and belongs where it is; these fourteen documents are the part worth keeping" is usually the true outcome.

### Then: contained or pointer?

**Does it have a live `.git`, or is anything actively writing to it?**

- **Yes → pointer area.** A `README.md` and `STATE.md` saying where it lives and how to work with it. Nothing copied, nothing moved, no risk to something that is running.
- **No → contained area.** **Copy, never move.** Verify the copy works before the original is touched at all.

Either way, the copying is the trivial part. **The work is reconciling what it duplicates.** Imported folders arrive with their own root files, their own inbox and archive, often their own task list or rulebook. Every duplicated role has to be resolved: which one governs, and what happens to the other. **A second task list is the one that matters most**: its open items become cards in `TASKS.md`, or the list gets a line on the board saying it is still live and where. A list nobody registered is open and invisible.

### Organised, or a pile?

**Cannot tell which? Treat it as organised: change nothing inside it, and ask.** The two paths prescribe opposite actions, so a wrong guess here is not a near miss. Guessing "pile" at an organised folder re-cuts somebody's working project, and that is the one move in this procedure that cannot be undone. An unnecessary question costs thirty seconds. If the owner is not available, leave the internal shape exactly as it is, carry on with everything outside it, and log the classification `assumed`.

**Already organised**: it has its own structure, and that structure works. **Leave it exactly as it is.** An area is sovereign inside itself: the system governs where it lives, its row on the board, its state file and the trust vocabulary, never its internal shape. Reconcile the collisions, add `README.md` and `STATE.md`, and stop.

**A pile**: things thrown in over months with no scheme. Importing it unchanged just relocates the mess. But **do not invent a structure for it either**:

1. **Group what is actually there** and show the owner the groups, in the words the files themselves use. Six clusters with counts beats a proposed folder tree.
2. **Ask which groups are worth keeping.** A real part of any pile is dead: superseded drafts, one-off downloads, things solved long ago. That question is the owner's.
3. **Route each group yourself.** Most of it will belong inside areas that already exist.
4. **A group becomes an area only if it is an area of their work**, not because it is large. When one appears, say what you noticed and let the owner name it.
5. **Anything that fits no group goes to `inbox/`.**

**Machine litter is not history.** Editor lock files (`~$…`), `.tmp`, `.DS_Store`, `Thumbs.db`, zero-byte scratch files: leave them behind during an import and say in one line what was skipped.

### Last: close the duplicate you just created

**"Copy, never move" leaves a second copy of everything, and an import that stops there is half-done in a way that looks finished.** So every contained take-in ends with the same closing step, in the same session:

1. **Hash every file in the original against the area.** Not a count, not a spot check: every file.
2. **Account for the difference.** A file that does not match is either genuinely absent, or was deliberately rewritten during the import. Say which, per file. "40 of 41 identical; the 41st is the README, rewritten and expanded, every original section present" is an accounting. "Looks fine" is not.
3. **State the verdict in one line and hand the decision over** as a *decide* card: *"The original is now fully redundant. Delete it, or keep it as a backup?"* **Never delete it unasked**, and never let the question quietly go unasked either.
4. **Log the answer in `DECISIONS.md`**, including "kept on purpose".

If anything is genuinely unique to the original, even one file, **rescue it before asking**, verify the hash of the rescued copy, and name it.

**And correct what the import already wrote.** An area `README.md` that says *"the original still exists"* becomes false the day it is deleted. A file that states something about the world carries the date it was true, and gets fixed when it stops being true.

## Verifying an import someone says already happened

**"That folder was already integrated" is not evidence; it is a memory**, and it is the most expensive sentence in this system, because the action it invites is deletion. Verify it, in two passes:

1. **By hash**: every file in the source against every file in the claimed destination. This finds what was copied untouched.
2. **By filename**: every file that failed pass 1, checked against every filename in the destination. **This is the pass people skip, and it is the one that matters**, because a file that arrived and was then edited would otherwise read as "missing" when it is fine.

Report three groups, never a single number:

| Group | Meaning |
|---|---|
| **Present, identical** | Copied and untouched. Safe |
| **Present under the same name, different content** | It arrived, then diverged. **A human decides which version is current**, never in bulk, in either direction |
| **Absent entirely** | No file of that name anywhere. It was never integrated |

**Anything in the third group means the claim was false, and the folder stays.** Say what is in it by subject rather than by count: *"the design document for every one of the seventeen features"* lands; "54 files" does not.

## When unsure

`inbox/`, with a line in the file's header saying what it is and why it was not routed. That is the right answer, not a failure to decide.
