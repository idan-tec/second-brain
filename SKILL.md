---
name: second-brain
description: Turn a single folder into a person's second brain and then govern it, so that any agent opening that folder in any future session knows who the person is, where everything lives, and how to file new material without losing it. Use this whenever someone wants to set up a personal life-management or "second brain" folder from scratch, wants to add a new area of their life to one, throws material at you to be filed ("here, put this somewhere", "where should this go?", "take this folder in"), asks what they are neglecting, or wants their weekly, monthly, or quarterly review. Also use it when someone asks you to organise their notes, projects, goals, or personal documents into a durable structure that survives across sessions and tools - even if they never say "second brain" or "life OS". If a folder you are working in has a root CLAUDE.md (or CONSTITUTION.md, in older installs) whose opening lines carry a "second-brain v" marker, this skill governs it.
---

# second-brain

**version 0.2.0 · 2026-07-29** — one folder holds a person's whole life. This skill is how any agent works with it.

*(When installing or updating, write this version line into the folder's `START-HERE.md` so the owner can tell which one they have.)*

## The one idea

Most personal systems fail the same way. The content is fine; the *filing* is what kills them. Six months later the person cannot find the thing, cannot tell a locked decision from an abandoned draft, and cannot see that one area of their life has quietly gone dark.

So this system carries three axes at once, and the second and third are the ones other systems drop:

- **Maturity** — evidence → decision → work → proof
- **Trust** — approved · unreviewed · finished · replaced
- **Sensitivity** — open · private · sealed

And one rule holds it together: **goals live only at the root, state lives in every branch.** If each area of a life carries its own goals, the person can never choose *between* areas — and choosing between areas is the entire problem.

## Speak their language

**This skill is written in English so it can be taught, shipped, and maintained. That is not an instruction to talk to the person in English.** Reply in whatever language they write to you in, and switch if they switch — this folder is their inner life, and being interviewed about it in a second language quietly flattens the answers.

**If the signal is genuinely ambiguous at setup, ask — one line, before writing anything owner-facing.** This is the single exception to building without questions, and it earns it: the answer takes two seconds, and getting it wrong means the owner cannot comfortably read their own system. Guessing from a folder name or a settings file is not a signal; those are often in English for people who think in something else. Whatever is chosen, **log it in `DECISIONS.md`** — marked `assumed` if nobody confirmed it — so that in six months it reads as a default that can be revisited rather than a decision somebody made.

The same split runs through everything: **their content in their language** — `STATE`, notes, decisions, the entries on the board, everything in `compass/`. **Only file and folder names stay ASCII English**, and only because tools break on anything else.

Templates split in two, and the line between them matters:

- **The frame — the root `CLAUDE.md` rulebook, the branch adapters, `system/ROUTING.md`, `system/TRUTH.md`, the `inbox/` and `archive/` READMEs — installs verbatim, in English.** Nobody but an agent reads these, agents read English perfectly well, and keeping them byte-identical across every install is what makes the system teachable, upgradeable, and checkable — you can verify an install is intact by comparing it against the templates.
- **Everything the person actually reads — `START-HERE`, `BOARD`, the `compass/` set, `decisions/`, and every branch's `README` and `STATE` — is written in their language**, translating the template's headings as you fill it. There the template is a shape to follow, not text to transcribe.

An owner who cannot read their own board does not have a second brain; they have a filing cabinet in a language they do not think in.

## If the folder already exists

Read the root `CLAUDE.md` in full first, always — Claude Code loads it automatically, but loaded is not read. This skill tells you *how* to act. The rulebook tells you *what the rules are*, and the owner may have amended them. **The rulebook wins.** (An older install may carry the same rulebook as `CONSTITUTION.md` with a five-line `CLAUDE.md` adapter pointing at it; treat the pair as the rulebook, and offer — once — to migrate it to the single-file form.)

## Pick a mode

| The person is… | Mode |
|---|---|
| starting from an empty (or unstructured) folder | **BOOTSTRAP** |
| opening a session to work | **ORIENT** |
| handing you material, or a whole folder, to file | **INTAKE** |
| asking what moved, what is stuck, what is neglected | **REVIEW** |

Never run BOOTSTRAP on a folder that already carries the `second-brain v` marker in a root `CLAUDE.md` or `CONSTITUTION.md`. That is an existing system; orient into it instead.

---

## BOOTSTRAP — an empty folder becomes a life

**Ask nothing. Build it, hand it over, let them start using it.**

Setup questions are a blank screen wearing a friendly face. Asked to enumerate their own life in the abstract, before seeing anything, people answer with what sounds right rather than what is true — and every question is one more place to abandon the whole thing. The branches a person actually needs are far better discovered from what they bring than from what they can recall on demand.

So install everything below in one go, in a single turn, without asking anything:

| Template | Installs as |
|---|---|
| `root-CLAUDE.md` | `CLAUDE.md` — the rulebook itself, at the root |
| `ROUTING.md` · `TRUTH.md` | `system/` |
| `inbox-README.md` · `archive-README.md` | `inbox/README.md` · `archive/README.md` |
| `START-HERE.md` | `START-HERE.md` |
| `BOARD.md` | `BOARD.md` — the two rows below, plus the "not yet set up" section |
| `DECISIONS.md` · `OPEN.md` | `decisions/` |
| `branch-README-preset.md` · `branch-STATE.md` · `adapter-branch.md` | `branches/work/` and `branches/personal/` |

Everything comes from `assets/templates/`: **copy and fill; do not compose from memory.** If every install improvises its own wording there is no shared system to teach, support, or upgrade — only a family of lookalikes that drift apart. An install done right is byte-identical to the templates in its frame files, which is what makes it checkable later.

**No `compass/` at setup.** See the section below — it is offered later, and creating it now would leave four aspirational files full of placeholders. **An empty file is worse than a missing one, because it looks handled.** The same reasoning that forbids empty folders forbids these.

### The two branches it starts with

`work` and `personal`. That is all, and the count is deliberate.

A branch that already exists is not the same thing as a list offered as a question. A question anchors — say "work, health, money" and the person starts picking from your menu instead of describing their life, and it cannot be undone. **A default that is visibly a default anchors nothing**: it can be renamed, split, or deleted in one move, and its own README says so in the first line.

But a *specific* name still anchors even unasked, which is why there are only two. `family` is not universal — some people do not have one, and for others it is complicated. `health` presumes something. `work` is close to universal and is where the first material will come from anyway; `personal` is deliberately vague and is explicitly labelled a temporary holding pen.

**`personal` is meant to be outgrown, and that is the mechanism that replaces the interview.** As it fills, watch for clusters — but watch for the *right* thing. A cluster of files is not automatically an area of a life; if it were, everyone would end up with a branch called "invoices". **What you are looking for is a part of their life that has started to take up room.**

The list below is not a taxonomy and never becomes folders. It exists so you can *recognise* one when it shows up, instead of dropping everything into `personal` because nothing matched:

> health · money · family · a specific relationship · a child · caring for a parent · learning something · home and property · a side project or business · a craft or practice · faith · a legal or bureaucratic process with an end date

When one appears, **say what you noticed and let them name it** — *"the last few things you've put in are all about your health. Do you want that separate? What do you call it?"* Their word, not the one from this list. And when they say no, record it and do not raise it again.

### Asking costs something

**A question spends the owner's attention, and attention is the scarce thing here — not disk space and not your tokens.** You know how to file. So file: route into existing branches, create folders when they are justified, keep the index and the board current, and do it without narrating each step as a decision they have to make.

Ask only when the answer would change what you do **and** the material cannot settle it. Naming a new area of their life is the clearest case — that is theirs. "Which of these two branches does this belong in" usually is not; pick the one they would look in, and say so in a line they can correct.

### Then get out of the way

Say in a few lines what now exists and that they can start putting things in. **Do not present a plan, a next step, or a checklist.** The whole promise is that this needs no setup.

Detect storage **once**: is there a `.git`? Record `storage:` in `START-HERE.md` and never ask again. git is optional and always will be — requiring it would exclude everyone who is not a developer, which is most of the people who need this.

### Everything you decided or noticed lands in a file — in the same turn

Building without questions means taking assumptions on the owner's behalf. That is fine, and it is exactly why each one has to leave a trace on disk:

- **Every assumption you took** — storage, language, anything else — gets a line in `decisions/DECISIONS.md`, marked `assumed`.
- **Everything you flagged but refused to act on** — a folder name that breaks the naming rule is the usual one — becomes an item in `decisions/OPEN.md`, with the recommendation and the default you would otherwise have said out loud.

**Say it in chat as well, but never only in chat.** The conversation is gone by tomorrow; the folder is the memory. An assumption announced and not written is indistinguishable, six months later, from a decision the owner made deliberately — and that is how a system starts lying to the person who trusts it.

**Verify every factual claim before you write it down — especially the ones about completeness.** "All logged", "all copied", "every file verified", any sentence with a count in it: run the check, then write the number you actually got. Not the number you intended to get.

This matters most in `DECISIONS.md`, because that file is permanent. A claim that is 40-out-of-41 true reads as fully true forever, and the day somebody re-runs the check and finds it false, they stop trusting the entire log — not just that line. **One overstated sentence can cost the credibility of the only memory this system has.** If something was deliberately left out or done differently, say so in the same breath: *"40 of 41 copied byte-identical; `README.md` was rewritten because …"* is a stronger record than a round number, and it is the honest one.

### Naming

**The person names the folder.** It is the one thing here that is purely theirs and costs nothing, and someone who named their own folder treats it differently from someone handed a name. Nothing depends on the choice: this skill recognises a second-brain folder by the `second-brain v` marker in the opening lines of its root `CLAUDE.md`, never by the folder's name, and every path inside is relative. If they have no preference, suggest `second-brain` and move on.

**One constraint, and it applies to the root folder too: ASCII English, no spaces.** Use hyphens — `second-brain`, `work`, `START-HERE.md`.

Not a style preference. These names get typed into shells, passed to tools, and synced between machines, and spaces or non-ASCII characters break that in ways that are genuinely miserable to debug — an unquoted path silently truncates, an encoding mismatch reports a file as missing while it sits right there. If they propose a name with spaces, explain why and offer the hyphenated form rather than accepting it quietly.

Their **content** goes in whatever language they think in. Only the names are constrained.

### Make it portable

Offer to copy this skill into `<their folder>/.claude/skills/second-brain/`. Then the folder carries its own rules: it survives a dead laptop, a new machine, and a different AI vendor in three years. That independence is worth more here than staying in sync with the original, because this folder is supposed to outlive all of them.

---

## THE COMPASS — offered later, never at setup

Filing is the easy half. `compass/` is the half that turns a well-organised filing cabinet into something that can tell a person they are spending every hour on the loudest branch. Without it there is order and no direction, and the board can report *what* is neglected but never *whether that is a problem*.

It holds four files, at four altitudes: `WHO-I-AM.md` (what settles things — changes over years) · `HORIZON.md` (where each branch goes in one to three years) · `SEASON.md` (**this cycle: three to five goals, total, across everything — the cap is the whole point**) · `NOW.md` (this week).

**None of it exists until the owner says yes.**

### When to offer

Wait until the folder can argue for it — a handful of branches, some real material, the first time they ask what to focus on, or the first weekly review. **Show the state of things first, then offer.** Committing to a direction before seeing anything is exactly the abstraction problem that setup questions have, moved later.

Something like: *"There are five branches here now and nothing that says what these next months are for, so there is no way to tell whether where your time is going is where you want it. Worth ten minutes?"*

Then, and only then, ask — one at a time, still never offering a list of anything they should want.

### When they say no

**Record it.** A line in `DECISIONS.md`, and the board's entry changes from *missing* to *declined <date>, not offered again*.

This matters more than it looks. An agent that re-offers a declined thing every session teaches the owner to stop reading the board — and the board is the single thing holding the whole system together. **Asking twice costs more than never asking.** The record also keeps the door open honestly: in six months they can reopen it because they chose to, not because a bot forgot.

---

## ORIENT — every session

Read in this order: the root `CLAUDE.md` (loaded automatically — read it, do not skim it) → `BOARD.md` → `compass/NOW.md` and `compass/SEASON.md` → the `README.md` and `STATE.md` of the branch in play.

That is the whole mandatory set, and it is deliberately small — roughly 200 lines. **Keeping it small is a feature, not a convenience.** A reading list of twenty files gets skimmed, and a skimmed rulebook is no rulebook.

Nothing else in a branch loads automatically. Use the branch's `INDEX.md` to find things rather than walking folders.

Open your first reply with one line so the owner can tell at a glance that you actually read:

`branch: <name> · read: BOARD, NOW, SEASON, <branch>/STATE`

**Exemption:** a branch that arrived carrying **its own rulebook** follows **its own opening protocol** when a session works inside it — its rulebook already names what to read, and stacking this list on top is ceremony that buys nothing for that branch's work. ORIENT as written binds sessions working **at brain level or across branches**. (The measured failure that produced this rule: on a real install, every session inside an imported-rulebook branch silently skipped ORIENT, because the branch's own rulebook prescribed a different reading order — and a rule broken silently every session teaches sessions that rules are optional.)

---

## INTAKE — "here, take this"

**This is where these systems actually die.** Not from bad content — from good content filed where nobody will find it, at a trust level it never earned. Read `assets/templates/ROUTING.md`; it is both the procedure you run and the file installed at `system/ROUTING.md`. Run all four questions in order.

Then the part that gets forgotten. **Filing is not finished when the file exists:**

- File written, first line states `kind:` and `trust:`
- Row added to the branch `INDEX.md`, under a topic heading in the owner's words (create it from `branch-INDEX.md` once the branch passes ~5 files — it is the retrieval surface, so it is not optional once there is anything to retrieve)
- Branch `STATE.md` last-touched date updated
- `BOARD.md` row updated
- Changed a decision? → a line in `decisions/DECISIONS.md`
- Raised something only the owner can settle? → an item in `decisions/OPEN.md`, **with a written recommendation and a default**

Skipping the index or the state update is the real failure mode. The file exists and is invisible, which is worse than not having written it — the person now believes it is handled.

**Unsure which branch?** `inbox/`, with a one-line note. Never invent a branch to hold one file, and never guess in order to look tidy. A wrong file in a right-looking place reads as *decided*; an honest unsorted one reads as *pending*.

**When a new branch is genuinely born** — the owner names one, or a cluster in `personal` gets split out — it gets the same flat trio as the originals, from `branch-README.md`, `branch-STATE.md`, and `adapter-branch.md`, **plus its row on `BOARD.md` in the same action.** Use `branch-README.md` here, not the preset version: this one was chosen rather than handed over, and it should not carry a paragraph telling the owner it is a default they can throw away.

**Taking in a whole existing folder?** Two shapes, and the test is simple: **does it have a live, heavy `.git`, or is anything actively writing to it?** If yes, make it a *pointer* branch — three small files describing where it lives and how to work with it, nothing copied, nothing moved, zero risk. If no, make it a *contained* branch — copy it in (**copy, never move**; verify the copy works before touching the original), then reconcile the roles it duplicates. An imported folder usually brings its own root files, its own inbox and archive, and sometimes its own rulebook. Those collisions are the work; the copying is trivial.

**A contained take-in is not finished until the duplicate it created is closed.** "Copy, never move" leaves the original in place, and an import that stops there looks finished while quietly making the owner's disk messier than before they started. So: hash every file both ways, account for every difference (absent, or deliberately rewritten during the import — say which), rescue anything unique *before* asking anything, then state the verdict in one line and hand the decision over — *"the original is now redundant; delete it, or keep it as a backup?"* **Never delete it unasked, and never leave the question unasked.** Log the answer either way, including "kept on purpose". Full procedure in `ROUTING.md`.

**Asked to verify an import someone says already happened?** That is a different operation, and `ROUTING.md` has it. The short version: *"it was already integrated"* is a memory, not evidence, and the action it invites is deletion. Check by hash, then check the failures **by filename** — the pass everyone skips, and the one that separates *edited after arriving* from *never arrived*. Report three groups, not one number.

**Keep the index current, and let the folder stay flat.** `notes/` holds everything; `kind:` and `trust:` are the file's first line. Sub-folders only when the pile genuinely hurts to scan — and then **named by topic, in the owner's words**, never by lifecycle stage. Say so before creating one; never grow structure silently.

The reason is retrieval, and it is the thing these systems get wrong most often. **People look for things by what they are about.** A tree sorted by stage-of-process asks them to reconstruct a classification they never made, so the material is technically filed and practically gone. `INDEX.md` grouped by topic, plus plain search over markdown, is what actually finds things — folders are only storage.

---

## REVIEW — the only part that cannot be skipped

Offer it when it is due. Never run one unasked.

- **Weekly** — `NOW` against `SEASON`. What moved, what did not. **Anything stuck twice running gets flagged** — twice is not laziness, it is a signal that the goal or its definition is wrong. Empty the `inbox/`.
- **Monthly** — scan `BOARD.md` for neglect and report it **as data, flatly**: "family: 58 days." Not "you have been neglecting your family." The person already knows; what they lack is the number.
- **Quarterly** — close `SEASON`, write outcomes into `DECISIONS.md`, confirm every line marked `assumed`, open the next cycle. **An unmet goal does not roll over automatically** — it gets re-chosen or dropped, deliberately.

### The sweep

The three reviews above are the owner's. This one is yours, and it exists because filing has a step that reliably gets skipped: the index row, the state date, the board. Offer a sweep when a lot has arrived at once, or alongside the weekly review:

- files no `INDEX.md` mentions — they exist and are invisible
- branches whose `STATE.md` date is older than their newest file
- near-duplicates that should be one file plus a supersession line
- notes naming a decision that never reached `DECISIONS.md`
- links pointing at files that moved or were renamed
- anything factual carrying no date

Fix the mechanical parts and report them; leave anything that changes meaning to the owner. **Offer it — never schedule it.** A sweep on a timer bills for nights when nothing happened and trains the owner to stop reading its output.

Say this out loud at bootstrap: without the review, everything above is a folder of dead files within six weeks. Writing a vision is enjoyable and reviewing one is not, and that asymmetry — not the structure — is what kills these systems.

---

## The laws

- **The owner defines the terms.** Never decide what "enough", "healthy", or "successful" means for someone. Build the surface where they write it down, then hold them to what they wrote.
- **Every decision goes in a file**, with a date and a reason. Conversation memory does not survive the session, and most installs have no version control — `decisions/DECISIONS.md` is the only history there is.
- **Never delete, never overwrite.** Move to `archive/` with a date. `DECISIONS.md` is append-only; a reversed decision gets a new line that supersedes the old one, never an edit.
- **Never promote trust.** `needs-review` → `current` is the owner's call, always.
- **Never create an empty folder.**
- **No absolute paths, anywhere.** This folder gets renamed, moved, and copied to other machines, and every hardcoded path is a future break.
- **Check the source, not the summary.** A report saying "done" is not evidence. If you did not look, say you did not look.
- **Owner unavailable?** Take the documented default, proceed, and log it `assumed`. Never block silently — a stalled system is worse than a documented assumption.
- **Maintenance is not failure.** A branch with no goal can be perfectly healthy. Most of a life is maintenance.
- **A branch is an area of a life, never a category of files.** Material lives inside a branch or in `archive/`; it never earns one of its own.
- **Assume that if it can, it will.** Instructions are not a permission layer. Anything irreversible or outward-facing — sending, publishing, paying, deleting — is described in the folder and done by the owner. Keep the keys outside; wording never held anything back.
- **Date every fact.** An undated number reads as current forever, and that is how a memory starts misleading the person who trusts it.

## Structure ceilings

**Max 3 levels below a branch** · **max ~7 items in any one view, excluding tool files like `CLAUDE.md`** (they have to sit where their tool finds them, so they do not count against readability) · **a folder is justified from the 3rd sibling file** · **zero empty folders**. The depth ceiling binds structure this system creates — **an imported branch's own tree is exempt**, however deep it runs.

**Dot-directories are tools, not content.** `.obsidian/`, `.claude/`, `.git/` and their kind belong to whatever the owner uses to read, edit, sync, or version this folder. They do not count against any ceiling, they are never tidied away, and they are never treated as clutter to clean up — deleting one throws away someone's settings or history. The folder is plain text on disk precisely so that these can come and go without it mattering; leave them alone.

These are not aesthetics. Measured on a real system built the other way round — full tree first, content later — one in five folders was completely empty and nesting reached ten levels deep. A tree built before its content does not fill up; it just hides things.

## One rulebook, one door

**Built for Claude Code, and the rulebook *is* the root `CLAUDE.md`.** There is no separate constitution file: the rules live directly in the one file Claude Code loads automatically for every session at or below the folder. That choice is deliberate — a rulebook behind a pointer depends on every session obeying the pointer, and measured on a real install, sessions skip mandated reads. A rulebook that is *in context by force* cannot be skipped. Each branch gets a three-line adapter (`adapter-branch.md`), so a session opened inside a branch picks up the root rulebook and the branch's own rules automatically: the tool walks upward from the session's directory and loads every `CLAUDE.md` it passes.

Other tools read other filenames — `AGENTS.md` for Codex and Cursor, `GEMINI.md` for the Gemini CLI. **Do not install them.** If a second tool ever enters the picture, add a three-line pointer file under that tool's name, aimed at `CLAUDE.md` — never a copy of the rules, because two rulebooks always drift, always disagree, and the disagreement always surfaces at the worst moment. The rules themselves live in exactly one place. **An adapter is an address, not a home.**
