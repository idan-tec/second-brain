# The rulebook — rules for any agent working in this folder

> **second-brain v0.2.** This file holds only what does not change between sessions.
> It carries the name `CLAUDE.md` so Claude Code loads it automatically for every session at or below this folder — the rules do not depend on anyone remembering to read them. The version marker above is also how the second-brain skill recognises this folder: by this line, never by the folder's name.
> Anything that changes — state, goals, what is active — lives in `BOARD.md`, `compass/`, and each branch's `STATE.md`. **Never put state here.**
> Ceiling: under 100 lines. It is read every session, so every line costs. Everything else loads on demand.

## 0. Opening a session

Before any action, in this order:

1. Read this file in full — loaded automatically is not the same as read; do not skim it.
2. Read `BOARD.md` — every branch, its state, and anything not yet set up.
3. **If `compass/` exists**, read `compass/NOW.md` and `compass/SEASON.md`. It is absent until the owner accepts the offer to build it, and its absence is normal, not a fault.
4. Read the `README.md` and `STATE.md` of the branch you are about to touch. **Nothing else in a branch loads automatically.**

Then open your first reply with: **`branch: <name> · read: BOARD, <compass files if present>, <branch>/STATE`**. If that line is missing, the owner knows you did not read.

**Exemption:** a branch that arrived carrying **its own rulebook** (§4) follows **its own opening protocol** when a session works inside it — its rulebook already tells the session what to read, and stacking this section's reads on top is ceremony that buys nothing for that branch's work. This section binds sessions working **at brain level or across branches**. A rule that is silently broken every session teaches sessions that rules are optional; this line replaces that breakage with a written boundary.

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
3. How far is it trusted? → `current` · `needs-review` · `completed` · `superseded` (see §4 for the two ways to say it)
4. How sensitive is it? → inherit the branch, and ask if this item is more sensitive than its home.

## 3. Who wins in a conflict

Full order: `system/TRUTH.md`. Highest first:

1. An explicit, recent decision by the owner
2. Verified reality — checked directly, never a report about it
3. `compass/` — WHO-I-AM > HORIZON > SEASON > NOW
4. A branch's `current/` material
5. `completed/` — evidence of the past, not an instruction for now
6. `needs-review/` — never authoritative until reviewed
7. `superseded/` and `archive/` — historical context only

**When intent and reality disagree, record the gap in `decisions/OPEN.md`.** Do not guess, and do not quietly pick a side.

## 4. Branch shape

**A branch is an area of a life. It is never a category of files.** The test is what the thing *is*: if the answer is a kind of file — backups, exports, invoices, screenshots, scripts — that is **material**, and material lives inside an existing branch or in `archive/`. It never earns a branch of its own. Only a life area does, and only the owner names one.

A branch is `README.md` + `STATE.md` + `CLAUDE.md` + **its own `OPEN.md`**, plus its material. **The branch `OPEN.md` holds what is open inside that branch only, with namespaced ids (`FIN-O1`); `decisions/OPEN.md` in the root holds ownership, money and anything crossing branches, and opens with the map of every list.** Two tiers on purpose: one list is right while there is a single working life in here, and stops being right the moment there is more than one business or more than one owner. **Like `INDEX.md`, it appears with its first item and not before** — an empty open list teaches people the list is empty. **A `README.md` also states whose business the branch serves** — not every branch in a folder like this belongs to the person who owns the folder, and an agent that assumes otherwise will hand someone else's material to the wrong party (`system/OWNERSHIP.md`, once there is a second party to map). **`CLAUDE.md` is normally a three-line adapter pointing here — but a branch that arrived carrying its own rulebook keeps it in that slot.** This root file loads for every session anywhere below it, so the branch is still addressed; forcing an imported rulebook out of the name its own project loads would break that project to satisfy this one. **The rulebooks are reconciled, never ranked.** A contradiction between them is a defect here, fixed here, and recorded in `decisions/OPEN.md` — never settled by an agent mid-session.

**The four trust words are fixed everywhere — `current` · `needs-review` · `completed` · `superseded` — but there are two valid ways to say them, and a branch uses one, never both:**

- **First-line label** (the default for a branch this system creates): everything lands in `notes/`, flat, and line one reads `kind: evidence | decision | work | proof · trust: <word> · <date if it states a fact>`.
- **Trust folders** (`current/` · `needs-review/` · `completed/`): for a branch that **arrived already organised that way.** Keep it. Re-cutting a working project to satisfy a house style destroys the muscle memory of whoever built it, and a copy reshaped away from its source stops being comparable to it.

**Folders are storage. `INDEX.md` is how anything is found.** People look for things by what they are *about*, never by which stage produced them. The index, grouped by topic in the owner's words, plus plain search across markdown, is the retrieval surface — and it is what makes either form above safe.

**Never invent a stage tree for material that arrived without one.** New sub-folders are named by topic in the owner's words. Propose; never grow structure silently.

Ceilings — **on structure this system creates, never on a branch's own imported tree**: **3 levels below a branch** · **~7 items per view, excluding tool files** · a folder is justified from the 3rd sibling · `INDEX.md` once a branch passes ~5 files.

**Goals never live in a branch, and neither does `NOW`.** They live in `compass/` only — `SEASON.md` and `NOW.md`. A branch may link to a goal; it never copies one. Two copies of a goal is two goals that will disagree, and **four `NOW` files are four things that are all urgent and nothing that chooses between them** — which is the only question a person with several branches actually needs answered. "The next step *here*" is `STATE.md`, and that is a different question.

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
