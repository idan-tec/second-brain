# CONSTITUTION — rules for any agent working in this folder

> **second-brain v0.1.** This file holds only what does not change between sessions.
> Anything that changes — state, goals, what is active — lives in `BOARD.md`, `compass/`, and each branch's `STATE.md`. **Never put state here.**
> Ceiling: under 100 lines. It is read every session, so every line costs. Everything else loads on demand.

## 0. Opening a session

Before any action, in this order:

1. Read this file in full.
2. Read `BOARD.md` — every branch, its state, and anything not yet set up.
3. **If `compass/` exists**, read `compass/NOW.md` and `compass/SEASON.md`. It is absent until the owner accepts the offer to build it, and its absence is normal, not a fault.
4. Read the `README.md` and `STATE.md` of the branch you are about to touch. **Nothing else in a branch loads automatically.**

Then open your first reply with: **`branch: <name> · read: BOARD, <compass files if present>, <branch>/STATE`**. If that line is missing, the owner knows you did not read.

## 1. Laws that never break

- **The owner defines the terms.** Never decide what "success", "healthy", "enough", or "important" means. Build the surface where the owner writes it, then hold them to what they wrote.
- **Every decision goes into a file** — `decisions/DECISIONS.md`, with date and reason. Conversation memory does not survive the session. Where there is no version control, that file is the only history that exists.
- **Never delete. Never overwrite.** Move to `archive/` with a date. `DECISIONS.md` is append-only; a reversed decision gets a new line, never an edit.
- **Never create an empty folder.** A folder is a by-product of its first file.
- **No absolute paths, ever.** This folder gets renamed, moved, and copied to other machines.
- **Unresolved goes to `inbox/`, not to a guess.** A wrong file in a right-looking place reads as decided, which is worse than honest and unsorted.
- **No secrets in this folder. Ever.** No passwords, API keys, tokens, account numbers, or `.env` files — not in a note, not imported with a folder, not "just for now". This folder syncs to a cloud drive and is read by agents; it is the wrong shape for anything whose value is that nobody else has it. Names, ownership, where a thing is managed, when it was last rotated — all fine. The value itself belongs in a password manager.
- **Assume that if it can, it will.** A rule written here is not a permission layer — it is a note to a system that may misread it. So the protection has to be that the capability is absent: if an agent working from this folder can send a message, move money, publish, or delete, then one day it will do so on a misread instruction, and no amount of careful wording prevents it. **Keep the keys outside.** Anything irreversible or outward-facing is described here and executed by the owner.
- **A fact without a date is a lie waiting to happen.** Any number, status, balance, count, or claim about the world carries the date it was true — right there in the line. Six months on, an undated figure reads as current, and the system starts confidently telling its owner things that stopped being true long ago. That is the specific way a memory turns into a liability.
- **Owner unavailable?** Take the documented default, proceed, log it `assumed`. Never block silently.

## 2. Where things go

Full procedure: `system/ROUTING.md`. **Read it before creating any file.** Short form, in order:

1. Which branch owns this? *(none fits → `inbox/`)*
2. Is it **evidence**, a **decision**, **work**, or **proof**? → `kind:` on line one
3. How far is it trusted? → `trust:` on line one — `current` · `needs-review` · `done` · `superseded`
4. How sensitive is it? → inherit the branch, and ask if this item is more sensitive than its home.

## 3. Who wins in a conflict

Full order: `system/TRUTH.md`. Highest first:

1. An explicit, recent decision by the owner
2. Verified reality — checked directly, never a report about it
3. `compass/` — WHO-I-AM > HORIZON > SEASON > NOW
4. A branch's `current/` material
5. `done/` — evidence of the past, not an instruction for now
6. `needs-review/` — never authoritative until reviewed
7. `superseded/` and `archive/` — historical context only

**When intent and reality disagree, record the gap in `decisions/OPEN.md`.** Do not guess, and do not quietly pick a side.

## 4. Branch shape

**A branch is an area of a life. It is never a category of files.** The test is what the thing *is*: if the answer is a kind of file — backups, exports, invoices, screenshots, scripts — that is **material**, and material lives inside an existing branch or in `archive/`. It never earns a branch of its own. Only a life area does, and only the owner names one.

A branch is `README.md` + `STATE.md` + `CLAUDE.md` (adapter) + `notes/`, and **everything filed goes into `notes/`, flat.** Kind and trust are the **first line of the file**, not folders around it:

`kind: evidence | decision | work | proof · trust: current | needs-review | done | superseded · <date if it states a fact>`

**Folders are storage. `INDEX.md` is how anything is found.** People look for things by what they are *about*, never by what stage of a process produced them — so a folder tree built on stages hides material behind a classification the owner never made and cannot recall. The index, grouped by topic in their own words, plus plain search across markdown, is the retrieval surface. Keep it current and the flat pile costs nothing.

Sub-folders appear only when the volume genuinely hurts to scan, and then they are named **by topic in the owner's words** — never by lifecycle stage. Propose; never grow structure silently.

Ceilings: **3 levels below a branch** · **~7 items per view, excluding tool adapters** · a folder is justified from the 3rd sibling · `INDEX.md` once a branch passes ~5 files.

**Goals never live in a branch.** They live in `compass/SEASON.md` only. A branch may link to a goal; it never copies one. Two copies of a goal is two goals that will disagree.

**A branch rule may add or tighten. It may never contradict this file.** If a branch needs to break a rule here, that is an amendment — an owner decision, logged in `DECISIONS.md`.

## 5. Sensitivity

Every branch `README.md` declares one line: `sensitivity: open | private | sealed`.

- `open` — normal.
- `private` — never quoted into summaries, artifacts, or anything leaving this folder.
- `sealed` — **do not read at all** unless the owner names this branch in the current session. Never send, publish, export, or include it anywhere.

This is a convention an agent honours, **not encryption**. Say so plainly if the owner assumes otherwise: anyone with access to the folder can read anything in it.

## 6. Rhythm

- **Weekly** — `NOW` against `SEASON`. Anything stuck twice running gets flagged.
- **Monthly** — scan `BOARD.md` for neglect. Report it as data, never as judgement.
- **Quarterly** — close `SEASON`, confirm every `assumed` line, open the next cycle.

Offer the review when it is due. Never run one unasked. Without it, all of the above is a folder of dead files within six weeks.
