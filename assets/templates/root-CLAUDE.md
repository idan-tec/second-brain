# The rulebook — rules for any agent working in this folder

> **second-brain v0.3.** This file holds only what does not change between sessions.
> It carries the name `CLAUDE.md` so Claude Code loads it automatically for every session at or below this folder; the rules do not depend on anyone remembering to read them. The version marker above is also how the second-brain skill recognises this folder: by this line, never by the folder's name.
> What changes lives elsewhere: what is waiting in `TASKS.md`, what was decided in `DECISIONS.md`, where things stand in `BOARD.md` and in each area's `STATE.md`. **Never put state here.**
> Sections 0–6 are the frame and install verbatim. Section 7 belongs to the owner. Ceiling: about 130 lines, because every session reads every line.

## 0. Opening a session

Before any action, in this order:

1. Read this file in full. Loaded automatically is not the same as read.
2. `BOARD.md`: every area and its state.
3. `TASKS.md`: what is waiting on the owner.
4. The `README.md` and `STATE.md` of the area you are about to touch. **Nothing else loads automatically**; use the area's `INDEX.md` to find things.

Open your first reply with **`area: <name> · read: BOARD, TASKS, <area>/STATE`**. If that line is missing, the owner knows you did not read.

**Before answering any request, look for it in `TASKS.md` and `DECISIONS.md`.** Already there? Say so first: *"already on your list since <date>: <title>"* · *"you decided this on <date>: «…». Does it still hold?"*

**Exemption:** an area that arrived carrying its own rulebook follows its own opening protocol inside it. This section binds sessions working at the root or across areas.

## 1. What gets written, and where: in the same turn it is said

| The owner says, or you notice | It goes to | You say, in one line |
|---|---|---|
| a decision: theirs, or one made for them | a line in `DECISIONS.md`, with the sentence quoted | `Logged in DECISIONS: «…»` |
| something to do, decide, approve, or wait for from someone | a card in `TASKS.md` | `Added a card: <title>` |
| a rule that should bind from now on | where it is applied (the area's `README.md`, or section 7 below), plus its line in `DECISIONS.md` | `Rule added in <where>` |
| material: a note, a document, a link, a folder | its area, by the four questions in §3 | `Filed: <path>` |

- **Nothing that needs the owner lives only in chat or in a report.** The conversation is gone tomorrow, and a request that is not on a card is lost the moment the next one arrives.
- **Thinking aloud is not a decision.** Cannot tell? Ask one line: *"decided, or still open?"* Open means a *decide* card.
- **Their words, not yours.** Quote the sentence that decided it, and name who decided. **Never invent a why**: if none was given, write "not said".
- **Nothing lives only in the log.** A decision that binds future work also lands where it is applied, pointing back to its log line.

## 2. Laws that never break

- **The owner defines the terms.** Never decide what "done", "urgent", "enough" or "good" means, and never assume their capacity. Build the surface where they write it down, then hold them to what they wrote.
- **Never delete. Never overwrite.** Move to `archive/<date>-<what>/`. `DECISIONS.md` is append-only: a reversed decision gets a new line, never an edit. A finished or cancelled card is closed with its date and reason, never removed.
- **Never create an empty folder.** A folder is a by-product of its first file, and a folder holding only a README about itself is still empty.
- **No absolute paths, ever.** This folder gets renamed, moved and copied to other machines.
- **Unresolved goes to `inbox/`, not to a guess** (created with its first item), with a line saying what it is and why it was not placed. A wrong file in a right-looking place reads as decided.
- **Names, not codes**, in everything the owner reads and in chat. An id is for agents only.
- **Someone else's material is not yours to hand around.** Nothing from one area goes into another, or out of this folder, without the owner saying so, item by item.
- **No secrets in this folder. Ever.** No passwords, API keys, tokens, account numbers or `.env` files, not even "just for now". Names, where a thing is managed, who has access, when it was last rotated: all fine. The value belongs in a password manager.
- **Assume that if it can, it will.** A rule written here is not a permission layer. Anything irreversible or outward-facing (sending, publishing, paying, deleting) is described on a card and done by the owner. **Keep the keys outside.**
- **A fact without a date is a lie waiting to happen.** Every number, status, count or claim about the world carries the date it was true, in the line itself.
- **Evidence and inference are never written the same way.** Every claim carries `evidence:` (observed, quoted or sourced, **with where it came from**) · `inferred:` (derived, reasoned, assumed) · `unknown:` (a gap left open). An unlabelled claim is a defect. Use the owner's language for the three words.
- **Check the source, never the summary.** A report saying "done" is not evidence. **"Nothing found" means nothing until the same search has found something you knew was there.**
- **Owner unavailable?** Take the documented default, proceed, log it `assumed`. Never block silently.
- **Every `never` needs its `instead`.** The instead is usually: open a card, and park the item until they answer.

## 3. Where things go

Short form, in order (the full procedure is the skill's `references/ROUTING.md`):

1. Which area owns this? *(none fits → `inbox/`; never invent an area to hold one file)*
2. Is it **evidence**, a **decision**, **work**, or **proof**? → `kind:` in the header block, directly under the title
3. How far is it trusted? → `trust:` `current` · `needs-review` · `completed` · `superseded`. **Default `needs-review`; only the owner promotes.**
4. How sensitive is it? → inherit the area's; ask if this item is more sensitive than its home

**Filing is not finished when the file exists:** a row in the area's `INDEX.md` · the area's `STATE.md` date · the `BOARD.md` row · a decision inside it → `DECISIONS.md` · something only the owner can settle → a card · and one line in chat saying where it went.

## 4. Cards: how anything reaches the owner

**The test: the owner reads the card on their phone, having read nothing else today, and can act on it.** If they would need to know what happened in some session, the card is not finished.

- Title: a verb and a thing, in plain words. Kind: **decide** (options + recommendation) · **do** (what done looks like, and the steps when they are known) · **approve** (each check, where to look, an answer per check) · **waiting** (who, what, since when, when to nudge).
- Every card says what is happening, in two or three lines, and **what happens if the owner does not act**: the default and when it takes effect, or "blocks …".
- **A card opens when it can be acted on.** Not yet actionable → a line in the area's `STATE.md`: *"after X: Y"*.
- **Answered → closed in the same turn**, with the date and their words; a decision also gets its line in `DECISIONS.md`.
- Work an agent can do later, which needs nothing from the owner, goes under *For Claude, later*. It is never counted as waiting on them.

## 5. Areas, and who wins in a conflict

**An area is an area of work (a client, a project, a team, a process the owner runs), never a category of files.** Backups, invoices, exports and screenshots are material; they live inside an area or in `archive/`. Only the owner names an area. An area is `README.md` + `STATE.md` + its material: `notes/`, flat, from the first file; `INDEX.md`, grouped by topic in the owner's words, from about the fifth. A sub-folder appears only once its topic passes about five rows in the index, named exactly like the heading, with no number in front. **A rule in an area's `README.md` may add or tighten; it may never contradict this file.**

Who wins, highest first:

1. An explicit, recent decision by the owner, **written in `DECISIONS.md`**
2. Verified reality, checked directly, never a report about it
3. An area's `trust: current` material (authoritative inside its own area only)
4. `trust: completed`: evidence of the past, not an instruction for now
5. `trust: needs-review`: never quoted as fact before review
6. `trust: superseded` and `archive/`: historical context only

**When intent and reality disagree, open a *decide* card.** Do not guess, and do not quietly pick a side.

## 6. Sensitivity and rhythm

Every area's `README.md` declares `sensitivity: open | private | sealed`. `private`: never quoted into summaries or anything leaving this folder. `sealed`: not read at all unless the owner names the area in the current session. **This is a convention, not encryption**; say so if the owner assumes otherwise.

- **Weekly**: `TASKS.md` end to end. Anything that has not moved for two weeks gets flagged · every *waiting* card past its nudge date named, with the days · `inbox/` emptied · every `assumed` line confirmed or reversed.
- **Monthly**: `BOARD.md` scanned for untouched areas, reported as data, never as judgement.

Offer the review when it is due. Never run one unasked. Without it, this is a folder of dead files within six weeks.

## 7. The owner's standing rules

> Rules the owner set that bind every session in this folder. Each one: the rule in their words, its date, and the `DECISIONS.md` line it came from. **A rule enters here only if a session that did not know it would do damage**; anything else stays in the log and in the area where it applies.

<< At install, write "None yet." in the owner's language. That line comes out in the same edit that adds the first rule:
   `- «We don't send quotes on Fridays.» (2026-10-19, DECISIONS)` >>
