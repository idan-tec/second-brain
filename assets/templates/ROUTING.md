# ROUTING — where anything goes

> **A procedure, not advice. Run it.**
> It exists because the failure that kills these systems is almost never bad content. It is good content filed where nobody will look for it, at a trust level it never earned.

## The four questions, in order

Never skip one, never reorder them. If a question cannot be answered, **stop and ask the owner.** Inferring here is how things get lost.

### Q1 · Which branch owns this?

- Fits exactly one branch → that branch.
- Fits two → the one the owner would **look in**, not the one it is *about*. Cross-link from the other.
- Fits none → `inbox/`. **Never invent a branch to hold one file.**

**Material never earns a branch.** If the honest answer to "what is this?" is a *kind of file* — backups, exports, invoices, screenshots, scripts, receipts — then it is material, and it belongs inside an existing branch or in `archive/`. A branch is an **area of a life**, and only the owner names one. The pull to open a branch is strongest exactly when nothing fits, which is exactly when it is wrong: what you have then is a pile with no home, and the answer to that is `inbox/`.

### Q2 · What kind of thing is it?

| `kind:` | The question it answers |
|---|---|
| **evidence** | something I found, was told, or measured |
| **decision** | something I chose, which now governs |
| **work** | something in progress right now |
| **proof** | something that happened, with a result |

**This is a label on the file's first line, not a folder.** Everything lands in `notes/`, flat.

Folders sorted by lifecycle stage fail the only test that matters: a person looking for something searches by what it is *about*, never by which stage of a process produced it. Filing by stage means retrieval requires reconstructing a classification the owner never made — which is how a well-organised folder becomes a place things disappear into.

**The trap worth naming:** a decision that arrives inside a working document is still a decision. Extract it. It also needs its line in `decisions/DECISIONS.md`, or in six months it is invisible and someone re-decides it differently.

### Q3 · How far is it trusted?

| `trust:` | Meaning |
|---|---|
| `current` | Approved, in force |
| `needs-review` | Might be right. **Never quoted as fact.** |
| `done` | Finished. Evidence of the past, not an instruction for now |
| `superseded` | Replaced. Historical context only |

Also a first-line label, for the same reason. **Default is `needs-review`.** Promotion to `current` belongs to the owner alone — an agent never promotes trust by itself, because a draft quoted as settled is indistinguishable from a fact until it causes damage.

### Q4 · How sensitive is it?

Inherit the branch's `sensitivity`. If this particular item is more sensitive than its branch, say so and ask — never file it quietly and hope.

---

## Keep the source, and link it

Two habits that cost a line each and are the difference between a record and a rumour:

**When you extract, keep what you extracted from.** A summary whose source is gone cannot be checked, and `TRUTH.md` asks you to check the source rather than the summary — a rule that is unenforceable the moment the source is discarded. So the extraction names its origin in its first lines, and if the origin is a file it stays alongside. If the origin is a conversation or a page, say so and give enough for someone to find it again.

**Link to what you would actually open.** These are markdown files, and a viewer like Obsidian turns `[[links]]` into a navigable graph — but only if the links exist. Link a note to the decision it supports, the person it concerns, the source it came from. **Do not link every term that happens to match**; a graph where everything connects to everything says nothing at all.

## Filing is not finished when the file exists

Every one of these, every time:

1. The file, with `kind:` and `trust:` on the first line — and, for anything factual, **the date it was true**.
2. **A row in the branch's `INDEX.md`** (created once the branch passes ~5 files).
3. **The branch's `STATE.md`** — at minimum, the last-touched date.
4. **The `BOARD.md` row.**
5. Changed a decision → **a line in `decisions/DECISIONS.md`.**
6. Raised something only the owner can settle → **an item in `decisions/OPEN.md`, with a recommendation and a default.**

**Steps 2 and 3 are the ones that actually get skipped**, and skipping them is the whole failure: the file exists, it is invisible, and the person now believes the thing is handled.

## Hard limits

- **Never create an empty folder.** It appears with its first file.
- **Three levels below a branch.** Deeper needs a written reason in the branch README.
- **About seven items per view**, excluding tool adapters. Past that, people stop scanning and start missing things.
- **A folder is justified from the third sibling.** One file does not get a house.
- **No absolute paths. Anywhere.**

## Taking in an entire existing folder

### First: is any of it content at all?

Before asking *how* to bring a folder in, sort what is inside it. A working directory is not a body of knowledge, and importing one wholesale turns a second brain into a junk drawer within a week. Four piles:

| Pile | Examples | What happens |
|---|---|---|
| **Never enters** | `.env`, key files, tokens, credentials, anything with a live secret in it | **Stays where it is. Not copied, not read beyond confirming what it is, not quoted.** Say it was left and why |
| **Not content** | `node_modules/`, `dist/`, `build/`, `.next/`, caches, lock files, `.tmp` | Skipped silently-but-stated. These were generated by a machine and can be regenerated by one |
| **Code and live projects** | anything with its own `.git`, anything being actively worked on | Pointer branch — see below. Never contained |
| **Actually knowledge** | notes, decisions, specs, research, documents, spreadsheets someone maintains by hand | This is what comes in |

**Say what landed in each pile.** The owner may disagree about one of them, and silent triage is indistinguishable from missing something.

**If the fourth pile is small — a dozen files out of thousands — say that plainly.** "Most of this is a development environment and belongs where it is; these fourteen documents are the part worth keeping" is a better outcome than a faithful import of somebody's build artifacts, and it is usually the true one.

### Then: contained or pointer?

**Does it have a live, heavy `.git`, or is anything actively writing to it?**

- **Yes → pointer branch.** Three small files saying where it lives and how to work with it. Nothing copied, nothing moved, no risk to something that is running.
- **No → contained branch.** **Copy, never move.** Verify the copy works before the original is touched at all.

Either way, the copying is the trivial part. **The work is reconciling what it duplicates** — imported folders arrive with their own root files, their own inbox and archive, often their own rulebook. Every duplicated role has to be resolved: which one governs, and what happens to the other.

### Organised, or a pile?

Folders arrive in one of two states, and they need opposite treatment.

**Already organised** — it has its own structure, and that structure works. **Leave it exactly as it is.** A branch is sovereign inside itself: the system governs where it lives, its row on the board, its state file and the trust vocabulary — never its internal shape. Re-cutting somebody's working project to satisfy a house style is tidiness for its own sake, and it destroys the muscle memory of the person who built it. Reconcile the collisions, add the three branch files, and stop.

**A pile** — things were thrown in over months with no scheme. Here the opposite is true: importing it unchanged just relocates the mess and quietly makes it the system's problem.

But **do not invent a structure for it either.** Instead:

1. **Group what is actually there** and show the owner the groups, using the words the files themselves use. Six clusters with counts beats a proposed folder tree, because it describes what they have rather than what you would have done.
2. **Ask which groups are worth keeping.** In a pile, a real part of it is genuinely dead — superseded drafts, one-off downloads, things solved long ago. That question is the owner's and it is the most valuable one here.
3. **Route each group yourself.** Most of it will belong inside branches that already exist. Do that work; do not narrate it as a series of questions.
4. **A group becomes a branch only if it is an area of their life** — not because it is a large group. Recognise the candidates (see the list in the skill), and when one appears, say what you noticed and let the owner name it.
5. **Anything that fits no group goes to `inbox/`**, not into a branch invented to hold it.

A pile is not a failure of the person. It is what happens when material arrives faster than anyone can file it — which is the entire reason this system exists.

**Machine litter is not history.** Editor lock files (`~$…`), `.tmp`, `.DS_Store`, `Thumbs.db`, zero-byte scratch files — these are artifacts an application dropped, not something anyone wrote. "Never delete" protects the owner's work, and treating a stray temp file as work to be preserved forever misreads the rule: it fills the archive with noise until the archive stops being worth opening. Leave them behind during an import and say in one line what was skipped, so the decision is visible rather than silent.

## When unsure

`inbox/`, with a one-line note on what it is and why it was not routed. That is the right answer, not a failure to decide.
