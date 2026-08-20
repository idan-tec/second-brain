---
name: second-brain
description: Turn a single folder into a person's second brain and then govern it, so that any agent opening that folder in any future session knows who the person is, where everything lives, and how to file new material without losing it. Use this whenever someone wants to set up a personal life-management or "second brain" folder from scratch, wants to add a new area of their life to one, throws material at you to be filed ("here, put this somewhere", "where should this go?", "take this folder in"), asks what they are neglecting, or wants their weekly, monthly, or quarterly review. Also use it when someone asks you to organise their notes, projects, goals, or personal documents into a durable structure that survives across sessions and tools - even if they never say "second brain" or "life OS". If a folder you are working in has a root CLAUDE.md (or CONSTITUTION.md, in older installs) whose opening lines carry a "second-brain v" marker, this skill governs it.
---

# second-brain

**version 0.2.4 · 2026-08-20** — one folder holds a person's whole life. This skill is how any agent works with it.

*(When installing or updating, write this version line into the folder's `START-HERE.md` so the owner can tell which one they have.)*

## The one idea

Most personal systems fail the same way. The content is fine; the *filing* is what kills them. Six months later the person cannot find the thing, cannot tell a locked decision from an abandoned draft, and cannot see that one area of their life has quietly gone dark.

So this system carries three axes at once, and the second and third are the ones other systems drop:

- **Maturity** — evidence → decision → work → proof
- **Trust** — approved · unreviewed · finished · replaced
- **Sensitivity** — open · private · sealed

And one rule holds it together: **goals live only at the root, state lives in every branch.** If each area of a life carries its own goals, the person can never choose *between* areas — and choosing between areas is the entire problem. **`NOW` follows the same rule for the same reason.** What is *open*, by contrast, does eventually split — see *When the folder outgrows its first shape* for what splits, what does not, and what triggers each.

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
| asking for a second brain to be set up | **BOOTSTRAP** |
| opening a session to work | **ORIENT** |
| handing you material, or a whole folder, to file | **INTAKE** |
| asking what moved, what is stuck, what is neglected | **REVIEW** |

Never run BOOTSTRAP on a folder that already carries the `second-brain v` marker in a root `CLAUDE.md` or `CONSTITUTION.md`. That is an existing system; orient into it instead.

---

## BOOTSTRAP — an empty folder becomes a life

### First: look at where you are standing

**BOOTSTRAP builds into the current folder only when it is empty** — or holds nothing but tool droppings (`.git`, `.obsidian`, `.claude`, `desktop.ini`, `.DS_Store` and their kind).

**If the folder already has real content, do not build into it.** A second brain installed on top of someone's existing files starts life owning material nobody routed: their documents sit next to `BOARD.md` with no branch, no index row, no trust label — invisible to the board, to the sweep, and to every review above. Measured on a real install: two content folders that pre-dated setup were still unrouted weeks later, because nothing ever looked at them. And the reverse risk is worse — a session "tidying" files it was never given.

Instead: **create a fresh sub-folder — `second-brain/`, unless the owner names something else — install there, and say plainly what you did and why.** The existing files are not touched, not moved, not read. If the owner later wants any of them inside, that is INTAKE — deliberate, one folder at a time, after the system exists. If the owner explicitly insists on installing into the non-empty folder itself, that is their call: record it in `DECISIONS.md`, and every pre-existing item gets a line on `BOARD.md`'s "not yet set up" list so nothing is silently invisible.

### Then build

**Ask nothing. Build it, hand it over, let them start using it.**

Setup questions are a blank screen wearing a friendly face. Asked to enumerate their own life in the abstract, before seeing anything, people answer with what sounds right rather than what is true — and every question is one more place to abandon the whole thing. The branches a person actually needs are far better discovered from what they bring than from what they can recall on demand.

So install everything below in one go, in a single turn, without asking anything:

| Template | Installs as |
|---|---|
| `root-CLAUDE.md` | `CLAUDE.md` — the rulebook itself, at the root |
| `ROUTING.md` · `TRUTH.md` | `system/` |
| `inbox-README.md` · `archive-README.md` | `inbox/README.md` · `archive/README.md` |
| `START-HERE.md` | `START-HERE.md` |
| `BOARD.md` | `BOARD.md` — with no rows in it, plus the "not yet set up" section |
| `DECISIONS.md` · `OPEN.md` | `decisions/` |

**That is the whole install. There is no row for `branches/`, because it is not created** — see below.

Everything comes from `assets/templates/`: **copy and fill; do not compose from memory.** If every install improvises its own wording there is no shared system to teach, support, or upgrade — only a family of lookalikes that drift apart. An install done right is byte-identical to the templates in its frame files, which is what makes it checkable later.

**No `compass/` at setup.** See the section below — it is offered later, and creating it now would leave four aspirational files full of placeholders. **An empty file is worse than a missing one, because it looks handled.** The same reasoning that forbids empty folders forbids these.

**And nothing else early either.** Seven things in this system are deliberately absent from a fresh install: `branches/` itself, `notes/`, a branch `INDEX.md`, a branch's own `OPEN.md`, a branch's own `archive/`, `system/OWNERSHIP.md`, and `compass/`. **Each is born with its first real item**, and each has a written trigger — the table in *When the folder outgrows its first shape*. Installing one early saves nothing later.

### It starts with no branches at all

**Nothing is created here for a person to fill in later** — not `work`, not `personal`, not the folder that would hold them.

Earlier versions of this skill installed those two, on the argument that a default which is visibly a default anchors nothing the way a setup question does. **Measured on a real install, both failed inside two weeks, in opposite directions.** `personal` was never used once — three skeleton files, retired at the owner's own request in the words *"they're empty and they bother me."* And `work` filled up with real material and still had to be renamed, because it described everything the person did and therefore described nothing: the board showed a branch that read as empty while it held the only copy of several working documents. **Two defaults, two failure modes, one folder.**

The reason is already written into every other rule here. **A branch that exists before its material is a shape waiting to be filled, and a tree built before its content does not fill up — it hides things.** A default branch is the setup question again, written to disk instead of asked out loud, and it is worse in one respect: a question can be ignored, while a folder sitting there reads as an instruction.

So `branches/` is born with the first branch, and the first branch is born from material. **That makes it the same rule as everything else in this system** — `notes/`, `INDEX.md`, a branch's own `OPEN.md`, `system/OWNERSHIP.md`, `compass/`. `branches/` was the last exception to it. There are now none.

**Where the first thing goes before any branch exists:** `inbox/`, which is installed on day one and is already the honest answer. Nothing is lost there, and nothing pretends to be filed.

**How the first branch is actually born.** The moment material plainly belongs to an area of a life — not a kind of file, an *area* — say what you noticed and let them name it: *"everything you've put in so far is about the same thing. Do you want it as its own area? What do you call it?"* **Their word, not yours.** That is the one question worth spending here, and it is the same question that creates every branch after it. Until it gets asked, the folder is honestly empty, which is a true thing to be.

**Watch for the right thing.** A cluster of files is not an area of a life; if it were, everyone would end up with a branch called "invoices". The list below is not a taxonomy, is never read out to the owner as a menu, and never becomes folders. It exists so you can *recognise* one when it turns up, instead of leaving everything in `inbox/` because nothing matched:

> health · money · family · a specific relationship · a child · caring for a parent · learning something · home and property · a side project or business · a craft or practice · faith · a legal or bureaucratic process with an end date

When they say no, record it and do not raise it again.

**And say what the board says on day one: nothing.** Zero rows, with a line stating that plainly and saying what makes the first one appear. An empty board is not a broken board.

### Asking costs something

**A question spends the owner's attention, and attention is the scarce thing here — not disk space and not your tokens.** You know how to file. So file: route into existing branches, create folders when they are justified, keep the index and the board current, and do it without narrating each step as a decision they have to make.

Ask only when the answer would change what you do **and** the material cannot settle it. Naming a new area of their life is the clearest case — that is theirs. "Which of these existing branches does this belong in" usually is not; pick the one they would look in, and say so in a line they can correct.

### Then get out of the way

Say in a few lines what now exists and that they can start putting things in. **Say plainly that there are no areas in it yet and that this is correct** — the first one appears when they bring something that belongs to one. **Do not present a plan, a next step, or a checklist.** The whole promise is that this needs no setup.

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

## WHEN THE FOLDER OUTGROWS ITS FIRST SHAPE

A fresh install fits one person, a couple of areas, and one list of open questions. Most folders stay there. **This section is everything that appears when that stops being true — each with the trigger that creates it, so nothing is ever built on a guess that it will be wanted one day.**

| What appears | The day it appears |
|---|---|
| `branches/` | the first branch — and the first branch is named by the owner, from material |
| `notes/` in a branch | the first file filed there |
| `INDEX.md` in a branch | roughly the fifth file |
| `archive/` inside a branch | the first time something *in that branch* is retired — a whole branch being retired goes to the root `archive/` instead |
| a branch's own `OPEN.md` | the first open question belonging to that branch alone |
| `system/OWNERSHIP.md`, and a `Whose business` column on the board | the first branch that is not the owner's |
| `compass/` | the owner says yes to the offer |

**None of these gets installed early "so it is ready."** A file that answers a question nobody has asked yet reads as an answer, and a reader cannot tell a placeholder from a decision.

### A second party arrives

It arrives quietly. Someone else's product the owner is paid to build. A relative's business running entirely on the owner's accounts. A client's material coming in for one job. **Nothing about the folder announces the change, and every rule in it was written assuming everything inside is the owner's.**

Two failures follow, and both have been measured on a real install. A document whose opening line declared it the one authoritative register of every identifier in the system listed someone else's business as a product of the wrong ecosystem, and was quoted as current for a month while being a month stale — **a file that declares itself the source of truth is not one.** And that same wrong claim had propagated *outside* the folder, into a user-level skill that loads in **every** project, where this folder's rulebook has no reach whatsoever. **Fix the outside copy in the same pass**, or the folder is right and the thing that actually loads is wrong.

When it happens:

- **Install `OWNERSHIP.md` into `system/`** from the template — one table for commercial ownership, one per activity for infrastructure, every field carrying the date it was true.
- **Add the `Whose business` column to `BOARD.md`**, filled for every row including the owner's own.
- **The branch `README.md` states whose it is on its second line**, beside sensitivity.
- **Write the ownership into `DECISIONS.md`** with the date and whose sentence it was. It is a fact about the world settled by the owner, not a property of a folder.

**The rule that costs the most to learn late:** a branch that is not the owner's is not the owner's to hand around, and **access in one activity never implies access in another** — even when the same person appears in both. When someone does appear in two activities in different roles, write the overlap down as a fact. Priority, rate and access all stop being neutral at that point, and none of it becomes harmless by being obvious.

**Keys still never enter the folder** — least of all another party's. `OWNERSHIP.md` records where a thing is managed and who can reach it. It never holds what they reach it with.

**Where there is nothing in writing between the parties, this map and the branch's open list are the entire memory of what was agreed.** They are not a substitute for an agreement and should never be described as one. What they can do is carry every change in rate, scope or inclusion on the day it is said, with the date — so the record is at least contemporaneous.

### One open list stops being enough

A fresh install has one list, and that is right while there is a single working life in here. **It stops being right the moment there is more than one business or more than one owner**, because "what is open" and "what is open on this one thing" become different questions, and one list can only answer the first.

**Split into two tiers. Never four:**

- **`decisions/OPEN.md` at the root** — ownership, money, the system itself, anything crossing branches. **It opens with the map: one row per open list in the folder, including any list an imported branch brought with it.** That map is the only surface answering *"what is open across everything"*, and a list missing from it is open and invisible.
- **A branch's own `OPEN.md`** — from `branch-OPEN.md`. What belongs to that branch alone, ids namespaced (`FIN-O1`) so no number is ever ambiguous between two lists.

**`DECISIONS.md` does not split with it**, and they look far more like a matching pair than they are. An open list is a working surface, read by whoever is on that one branch. The log is the history of the whole folder and gets read end to end. History split four ways stops being readable as history.

**`NOW` does not split either, for the opposite reason:** it is the one file whose entire job is choosing between branches, and four of them would be four things that are all urgent and nothing that chooses. *"The next step here"* is `STATE.md`, and that is a different question.

**Leave existing ids where they are.** Renumbering breaks every reference ever written to them, and those references sit in files nobody is going to re-read. Migration is a deliberate, logged decision — and *"these were left unmigrated on purpose"* is a legitimate line in the map.

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
- Changed a decision? → a line in `decisions/DECISIONS.md` — **one log, always the root one, whatever branch it came from**
- Raised something only the owner can settle? → an item in an open list, **with a written recommendation and a default**. Which list, once there is more than one: *When the folder outgrows its first shape*, below

Skipping the index or the state update is the real failure mode. The file exists and is invisible, which is worse than not having written it — the person now believes it is handled.

**Unsure which branch?** `inbox/`, with a one-line note. Never invent a branch to hold one file, and never guess in order to look tidy. A wrong file in a right-looking place reads as *decided*; an honest unsorted one reads as *pending*.

**When a branch is genuinely born** — the owner names one, or a cluster in `inbox/` turns out to be an area of their life — it gets the flat trio from `branch-README.md`, `branch-STATE.md` and `adapter-branch.md`, **plus its row on `BOARD.md` in the same action.** **If it is the first, it creates `branches/` too**, and the board's "no branches yet" paragraph comes out in the same edit — a folder that now has an area in it should never still be telling its owner that it has none.

**Taking in a whole existing folder?** Two shapes, and the test is simple: **does it have a live, heavy `.git`, or is anything actively writing to it?** If yes, make it a *pointer* branch — three small files describing where it lives and how to work with it, nothing copied, nothing moved, zero risk. If no, make it a *contained* branch — copy it in (**copy, never move**; verify the copy works before touching the original), then reconcile the roles it duplicates. An imported folder usually brings its own root files, its own inbox and archive, and sometimes its own rulebook. Those collisions are the work; the copying is trivial.

**A contained take-in is not finished until the duplicate it created is closed.** "Copy, never move" leaves the original in place, and an import that stops there looks finished while quietly making the owner's disk messier than before they started. So: hash every file both ways, account for every difference (absent, or deliberately rewritten during the import — say which), rescue anything unique *before* asking anything, then state the verdict in one line and hand the decision over — *"the original is now redundant; delete it, or keep it as a backup?"* **Never delete it unasked, and never leave the question unasked.** Log the answer either way, including "kept on purpose". Full procedure in `ROUTING.md`.

**Asked to verify an import someone says already happened?** That is a different operation, and `ROUTING.md` has it. The short version: *"it was already integrated"* is a memory, not evidence, and the action it invites is deletion. Check by hash, then check the failures **by filename** — the pass everyone skips, and the one that separates *edited after arriving* from *never arrived*. Report three groups, not one number.

**Keep the index current, and let the folder stay flat.** `notes/` holds everything; `kind:` and `trust:` are the file's first line. Sub-folders only when the pile genuinely hurts to scan — and then **named by topic, in the owner's words**, never by lifecycle stage. Say so before creating one; never grow structure silently.

The reason is retrieval, and it is the thing these systems get wrong most often. **People look for things by what they are about.** A tree sorted by stage-of-process asks them to reconstruct a classification they never made, so the material is technically filed and practically gone. `INDEX.md` grouped by topic, plus plain search over markdown, is what actually finds things — folders are only storage.

**There are two valid ways to say trust, and a branch uses one of them, never both.** A branch this system creates uses the first-line label: flat `notes/`, `kind:` and `trust:` on line one. **A branch that arrived already sorted into `current/` · `needs-review/` · `completed/` keeps its folders** — the four words are fixed everywhere and mean the same thing in either form. Re-cutting a working project to match the house style destroys the muscle memory of whoever built it, and a copy reshaped away from its source stops being comparable to it. **What is never allowed is one branch using both**, because then a file's trust has two answers and nothing says which is stale. `INDEX.md` is what makes either form findable, which is why it is the part that is not optional.

---

## REVIEW — the only part that cannot be skipped

Offer it when it is due. Never run one unasked.

- **Weekly** — `NOW` against `SEASON`. What moved, what did not. **Anything stuck twice running gets flagged** — twice is not laziness, it is a signal that the goal or its definition is wrong. Empty the `inbox/` — **and early on this is where branches get born**, because a week's worth of material shows what someone's life is actually made of far better than they could have said on day one.
- **Monthly** — scan `BOARD.md` for neglect and report it **as data, flatly**: "family: 58 days." Not "you have been neglecting your family." The person already knows; what they lack is the number.
- **Quarterly** — close `SEASON`, write outcomes into `DECISIONS.md`, confirm every line marked `assumed`, open the next cycle. **An unmet goal does not roll over automatically** — it gets re-chosen or dropped, deliberately.

### The sweep

The three reviews above are the owner's. This one is yours, and it exists because filing has a step that reliably gets skipped: the index row, the state date, the board. Offer a sweep when a lot has arrived at once, or alongside the weekly review:

- files no `INDEX.md` mentions — they exist and are invisible
- branches whose `STATE.md` date is older than their newest file
- near-duplicates that should be one file plus a supersession line
- notes naming a decision that never reached `DECISIONS.md`
- links pointing at files that moved or were renamed — **skipping `archive/` and reporting its count separately.** An archived document is a photograph of a moment; its dead links are evidence, and repairing them falsifies the record
- an open list with no row in the map at the top of `decisions/OPEN.md` — open and invisible, which is the open-question version of a file no index mentions
- anything factual carrying no date
- **the same number or rule stated in two places** — a target, a cadence, a count, a cap. One of them is already wrong or shortly will be. Do not reconcile them into a matching pair; pick the home, and turn the other into a link
- **and check inside single files, not only across them.** A document updated in one section and not another contradicts itself, which is harder to see than two files disagreeing and reads as authoritative either way. Every measured instance of this so far has been a number that was replaced hours after it was first written, in a document nobody re-read from the top

Fix the mechanical parts and report them; leave anything that changes meaning to the owner. **Offer it — never schedule it.** A sweep on a timer bills for nights when nothing happened and trains the owner to stop reading its output.

Say this out loud at bootstrap: without the review, everything above is a folder of dead files within six weeks. Writing a vision is enjoyable and reviewing one is not, and that asymmetry — not the structure — is what kills these systems.

---

## The laws

- **The owner defines the terms.** Never decide what "enough", "healthy", or "successful" means for someone. Build the surface where they write it down, then hold them to what they wrote. **Their capacity is one of those terms.** An ordinary working week is an assumption, not a fact — measured here, an agent computed an alarm from one, called a commitment "most of the week" when it was about a third, and had to be corrected by the owner. An alarm raised against an invented baseline costs more than no alarm, because it spends the one thing this system runs on: the owner still believing what it tells them. If it is not written down, ask.
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
- **No secrets in the folder. Ever.** No passwords, API keys, tokens, account numbers or `.env` files — not in a note, not carried in with an imported folder, not "just for now". A folder that syncs to a cloud drive and is read by agents is the wrong shape for anything whose entire value is that nobody else holds it. **Names, ownership, where a thing is managed, who has access, when it was last checked — all fine.** The values belong in a password manager. **Check for this at intake rather than trusting it**, because a real project brings its own, and an import is exactly how they get in.
- **A prohibition with no replacement gets filled by a guess.** *"Never invent this"* says what not to do and leaves the gap standing, and an agent missing a detail does not stop — it fills with the plausible thing and keeps building on it. The plausible one is the dangerous one, precisely because it does not look like a mistake. **Every `never` written into this folder needs its `instead` next to it**, and the instead is usually *ask the owner, and park the item until they answer*.

## Structure ceilings

**Max 3 levels below a branch** · **max ~7 items in any one view, excluding tool files like `CLAUDE.md`** (they have to sit where their tool finds them, so they do not count against readability) · **a folder is justified from the 3rd sibling file** · **zero empty folders**. The depth ceiling binds structure this system creates — **an imported branch's own tree is exempt**, however deep it runs.

**Dot-directories are tools, not content.** `.obsidian/`, `.claude/`, `.git/` and their kind belong to whatever the owner uses to read, edit, sync, or version this folder. They do not count against any ceiling, they are never tidied away, and they are never treated as clutter to clean up — deleting one throws away someone's settings or history. The folder is plain text on disk precisely so that these can come and go without it mattering; leave them alone.

These are not aesthetics. Measured on a real system built the other way round — full tree first, content later — one in five folders was completely empty and nesting reached ten levels deep. A tree built before its content does not fill up; it just hides things.

## One rulebook, one door

**Built for Claude Code, and the rulebook *is* the root `CLAUDE.md`.** There is no separate constitution file: the rules live directly in the one file Claude Code loads automatically for every session at or below the folder. That choice is deliberate — a rulebook behind a pointer depends on every session obeying the pointer, and measured on a real install, sessions skip mandated reads. A rulebook that is *in context by force* cannot be skipped. Each branch gets a three-line adapter (`adapter-branch.md`), so a session opened inside a branch picks up the root rulebook and the branch's own rules automatically: the tool walks upward from the session's directory and loads every `CLAUDE.md` it passes.

Other tools read other filenames — `AGENTS.md` for Codex and Cursor, `GEMINI.md` for the Gemini CLI. **Do not install them.** If a second tool ever enters the picture, add a three-line pointer file under that tool's name, aimed at `CLAUDE.md` — never a copy of the rules, because two rulebooks always drift, always disagree, and the disagreement always surfaces at the worst moment. The rules themselves live in exactly one place. **An adapter is an address, not a home.**

### The same rule binds skills, and that is where it actually breaks

A folder like this accumulates skills of its own — a procedure the owner runs often enough to be worth packaging, living in `<folder>/.claude/skills/`. **A skill is a trigger and a procedure. It is never a second home for a rule.**

The failure is specific and it has been measured. On a real install, a folder-local skill grew to 202 lines by restating the documents it pointed at — the same laws, the same format rules, the same targets — while *also*, in its opening paragraph, mandating that those documents be read in full every time. Two weeks later it carried **two contradictory targets for the same number, both dated the same day**: one matched the document, the other was a leftover of a decision replaced hours after it was written. A session reading only the skill would have reported against the wrong number with no way to know. The redundancy that was supposed to be a safety net was the thing that lied.

**The owner's own test settles what goes where, and it is better than any rule about it:**

> *If there is any chance you would ever want to read it or fix it yourself, it is a document. If only an agent would ever execute it, it belongs in the skill.*

So a folder-local skill legitimately holds **when it wakes up** (its `description`), **what to read and in what order**, **the procedure nobody but the agent runs**, and **the shape of its output**. It holds no laws, no targets, no numbers, no restated rules. Those live in the documents — once, where the owner can see them and fix them without opening a config file.

**One exception, and keep it to one:** a rule whose violation harms someone *outside* the folder may be flagged in the skill by name and severity, pointing at the document. A flag is an address; a summary is a second copy.

**Correct one thing when this comes up, because the owner will usually raise it as a token problem and it is not.** Only a skill's frontmatter `description` enters a session; the body loads when the skill triggers. A 200-line skill costs almost nothing per session. **The reason to cut it is drift, not context** — and saying so matters, because someone who believes they are saving tokens will fix the file once and let it grow straight back.
