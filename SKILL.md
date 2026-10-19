---
name: second-brain
description: Turn a single folder into a person's second brain for their work, and then govern it, so that any agent opening that folder in any future session knows what the person has decided, what is waiting on them, what they are waiting for from others, and where everything lives. Use this whenever someone wants a work "second brain" set up from scratch; says something that is a decision ("from now on…", "we're going with…", "my manager decided…"); mentions a task, a deadline, something to approve or something they are waiting for from someone; asks "what's waiting on me", "what did we decide about X" or "where is Y"; throws material at you to be filed ("here, put this somewhere", "take this folder in"); or wants their weekly review. Also use it when someone asks you to organise their work notes, decisions or to-dos into a durable structure that survives across sessions, even if they never say "second brain". If a folder you are working in has a root CLAUDE.md whose opening lines carry a "second-brain v" marker, this skill governs it.
---

# second-brain

**version 0.3.0 · 2026-10-19** — one folder holds a person's work: what they decided, what is open, and what is waiting on them. This skill is how any agent works with it.

*(When installing or updating, write `second-brain 0.3.0 · 2026-10-19` into the folder's `START-HERE.md` so the owner can tell which one they have. The marker in the rulebook, `second-brain v0.3`, names only the minor version, and changes only when the rulebook's frame does.)*

## The one idea

Work rarely gets lost because it was done badly. It gets lost in between: a decision said in a meeting and never written down, a task promised in passing, a question asked once that vanished the moment the next one came up, a document that exists and that nobody can find. Six months on, the person cannot tell what was decided from what was only discussed, or say what they are still waiting for, and from whom.

So the folder holds three things, each in exactly one place:

| What | Where | Shape |
|---|---|---|
| **What was decided** | `DECISIONS.md` | append-only, dated, in the words of whoever decided |
| **What is waiting on me** | `TASKS.md` | one list; every item is a card the person can act on from their phone |
| **Where each area of work stands** | `BOARD.md`, and a `STATE.md` per area | status, never history |

Everything else is material, filed into the area it belongs to and found again through that area's index.

**One rule holds it together: the person never has to know where things go.** You hear the decision inside the sentence, the task inside the complaint, the open question inside the aside, and you write it down in their words, in the same turn, and say in one line where it went. A system the person has to feed by hand is a system they stop feeding in the second week.

**What this is not:** a project manager, a planner or a goal tracker. There are no goals, visions or cycles in here, on purpose. It holds the part of work that otherwise lives only in someone's head: what they decided, what is open, what they owe and what they are owed.

## Speak their language

**This skill is written in English so it can be taught, shipped and maintained. That is not an instruction to talk to the person in English.** Reply in whatever language they write to you in, and switch if they switch.

**If the signal is genuinely ambiguous at setup, ask, in one line, before writing anything the owner will read.** It is the single exception to building without questions: the answer takes two seconds, and getting it wrong means the owner cannot comfortably read their own system. A folder name or a settings file is not a signal; those are often in English for people who think in something else. Whatever is chosen, **log it in `DECISIONS.md`**, marked `assumed` if nobody confirmed it.

The same split runs through everything: **their content in their language**: decisions, cards, the board, every area's `README` and `STATE`, the notes. **Only file and folder names stay ASCII English**, and only because tools break on anything else.

Templates split in two:

- **The frame, which is the whole root `CLAUDE.md` except what goes under its last two headings, installs verbatim, in English.** Nobody but an agent reads it, agents read English perfectly well, and keeping it byte-identical across installs is what makes the system teachable, upgradeable and checkable.
- **Everything the person reads (`START-HERE`, `BOARD`, `TASKS`, `DECISIONS`, every area's `README` and `STATE`) is written in their language.** In a language other than English, *copy and fill* means: keep the template's structure, with every heading, field and rule present, translated; add nothing from memory, drop nothing.

**A handful of words are vocabulary, not prose:** the four card kinds (decide · do · approve · waiting), the four trust words, the three claim labels (evidence · inferred · unknown), and `assumed`. At setup, choose one word for each in their language and write them under section 8 of the rulebook, *This folder's words*. Every session reads that section, so every session writes, and searches for, the same words. A session that picks its own translation writes cards that the next session's search cannot find. In an English folder, the section says so in one line.

**In a language that marks gender**, follow the form the person uses about themselves; until they have used one, write neutral forms.

## If the folder already exists

Read the root `CLAUDE.md` in full first, always. Claude Code loads it automatically, but loaded is not read. This skill tells you *how* to act; the rulebook tells you *what the rules are*, and the owner may have amended them. **The rulebook wins.**

**An install from v0.2 or earlier looks different** (`decisions/`, `system/`, `branches/`, perhaps `compass/`). It is still governed by its own rulebook, so follow that. Never migrate it silently. If the owner wants the new shape, that is a deliberate, logged decision, carried out one file at a time. **`compass/` is the owner's own writing, and a migration never touches it.**

## Pick a mode

| The person is… | Mode |
|---|---|
| asking for a second brain to be set up | **BOOTSTRAP** |
| opening a session to work | **ORIENT** |
| saying something that is a decision, a task, or something they are waiting for | **CAPTURE** |
| handing you material, or a whole folder, to file | **INTAKE** |
| asking what is waiting, what is stuck, what moved | **REVIEW** |

**Nobody asks for CAPTURE. It runs inside every other mode.** A decision mentioned in passing during an intake is still a decision, and a task mentioned during a review is still a task.

Never run BOOTSTRAP on a folder that already carries the `second-brain v` marker in a root `CLAUDE.md`. That is an existing system; orient into it instead.

---

## BOOTSTRAP — an empty folder becomes a work brain

### First: look at where you are standing

**BOOTSTRAP builds into the current folder only when it is empty**, or holds nothing but tool droppings (`.git`, `.obsidian`, `.claude`, `desktop.ini`, `.DS_Store` and their kind).

**If the folder already has real content, do not build into it.** A system installed on top of someone's existing files starts life owning material nobody routed: their documents sit next to `BOARD.md` with no area, no index row and no trust label, invisible to the board and to every review. Instead, **create a fresh sub-folder (`second-brain/`, unless the owner names something else), install there, and say plainly what you did and why.** The existing files are not touched, moved or read. If the owner later wants any of them inside, that is INTAKE: deliberate, one folder at a time. If the owner insists on installing into the non-empty folder itself, that is their call. Record it in `DECISIONS.md`, and give every pre-existing item a line on the board so nothing is silently invisible.

### Then build

**Ask nothing. Build it, hand it over, let them start using it.** Setup questions are a blank screen wearing a friendly face: asked to enumerate their work in the abstract, people answer with what sounds right rather than what is true. The areas a person actually has are far better discovered from what they bring than from what they recall on demand.

Install all of this in one go, in a single turn:

| Template | Installs as |
|---|---|
| `root-CLAUDE.md` | `CLAUDE.md`: the rulebook, at the root |
| `START-HERE.md` | `START-HERE.md`: the one file a human opens |
| `BOARD.md` | `BOARD.md`: no rows yet |
| `TASKS.md` | `TASKS.md`: one card, the copy question (*Make it portable*, below) |
| `DECISIONS.md` | `DECISIONS.md`: holding only the assumptions this setup took |

**Five files at the root, and not one folder. That is the whole install.** The rulebook's sections 7 and 8 are filled in the same turn: *"None yet."* under 7, and the folder's words under 8.

Everything comes from `assets/templates/`: **copy and fill; do not compose from memory.** If every install improvises its own wording there is no shared system to teach, support or upgrade, only a family of lookalikes that drift apart.

**No folders at setup, because none of them would hold anything yet.** Earlier versions installed `decisions/`, `system/`, `inbox/` and `archive/` on day one. The owner of the first real install judged most of them unused, and they were taken out of the install (2026-10-19): an inbox and an archive holding nothing but a README about themselves, and a `system/` folder of procedures that only an agent ever opened. **A folder that holds only its own explanation is an empty folder with a label on it**, and a tree built before its content does not fill up; it hides things. So every folder is now born with its first real item, like everything else here (*What appears later*, below). The procedure only an agent runs (where things go, how to take in a folder) lives in this skill, in `references/ROUTING.md`, not in the person's folder.

### It starts with no areas at all

**Nothing is created for a person to fill in later.** Not `work`, not `projects`, not the folder that would hold them.

A default area is the setup question again, written to disk instead of asked aloud, and it is worse: a question can be ignored, while a folder sitting there reads as an instruction. Measured on a real install of an earlier version, both of its defaults failed inside two weeks in opposite directions. One was never used once. The other filled up and still had to be renamed, because it described everything the person did and therefore described nothing.

**Where the first things go before any area exists:** decisions to `DECISIONS.md`, tasks to `TASKS.md`, and material to `inbox/`, which is created with its first item. Nothing is lost there, and nothing pretends to be filed.

**How the first area is born.** The moment material plainly belongs to one area of their work (not a kind of file, an *area*), or the same client or project keeps coming up in what they say, say what you noticed and let them name it: *"Everything you've put in so far is about the same client. Do you want it as its own area? What do you call it?"* **Their word, not yours.** That is the one question worth spending here, and it is the same question that creates every area after it.

**Watch for the right thing.** A cluster of files is not an area of work. If it were, everyone would end up with an area called "invoices". This list is not a taxonomy, it is never read out as a menu, and it never becomes folders. It exists so you can *recognise* an area when one turns up:

> a client · a project · a product · a team they lead · a process they own (hiring, payroll, purchasing, onboarding) · a supplier · a recurring report · a course they teach · a side business

When they say no, record it and do not raise it again.

**And say what the board says on day one: nothing.** Zero rows, with a line stating that plainly and saying what makes the first one appear, and one card, the copy question. An empty board is not a broken board.

### Asking costs something

**A question spends the owner's attention, and attention is the scarce thing here.** You know how to file. So file: route into existing areas, open cards, log decisions, keep the index and the board current, and do it without narrating each step as a decision they have to make.

Ask only when the answer would change what you do **and** the material cannot settle it. Naming a new area is the clearest case; that is theirs. "Which of these areas does this belong in" usually is not: pick the one they would look in, and say so in a line they can correct.

### Then get out of the way

**The hand-over is a few lines, in their language, and it says exactly this:**

1. what now exists: five files, no folders, and which one they open (`START-HERE.md`);
2. **that there are no areas yet, and that this is correct**: the first one appears when they bring something that belongs to one;
3. that there is one card waiting, the copy question, and what happens if they ignore it;
4. which assumptions you logged, in one line;
5. **that without the weekly review this is a folder of dead files within six weeks.** Capturing is easy and reviewing is not, and that asymmetry, not the structure, is what kills these systems.

Then stop. Do not present a plan, a next step or a checklist beyond that. The whole promise is that this needs no setup.

Detect storage **once**: is there a `.git`? Write what you saw in `START-HERE.md` (*git: yes* or *git: no*, with the date) and never ask again. That is an observation, not an assumption, so it does not also go in the log. Do not guess at cloud sync: it cannot be seen from inside the folder. git is optional and always will be; requiring it would exclude most of the people who need this.

### Everything you decided or noticed lands in a file, in the same turn

Building without questions means taking assumptions on the owner's behalf. That is fine, and it is exactly why each one has to leave a trace on disk:

- **Every assumption you took** (the language, if nobody confirmed it, the folder's words, anything else) gets a line in `DECISIONS.md`, marked `assumed`, with the basis: what you saw, and what you assumed from it.
- **Everything you flagged but refused to act on** (a folder name that breaks the naming rule is the usual one) becomes a *decide* card in `TASKS.md`, with your recommendation and the default, and the hand-over names it alongside the copy question.

**Say it in chat as well, but never only in chat.** The conversation is gone by tomorrow; the folder is the memory.

**Verify every factual claim before you write it down, especially claims about completeness.** "All logged", "all copied", any sentence with a count in it: run the check, then write the number you actually got. `DECISIONS.md` is permanent, and a claim that is 40-out-of-41 true reads as fully true forever. The day somebody re-runs the check, they stop trusting the whole log. *"40 of 41 copied byte-identical; `README.md` was rewritten because …"* is the stronger record, and the honest one.

### Naming

**The person names the folder.** Nothing depends on the choice: this skill recognises a second-brain folder by the `second-brain v` marker in its root `CLAUDE.md`, never by the folder's name, and every path inside is relative. If they have no preference, suggest `second-brain`.

**One constraint, for every folder and file name: ASCII English, no spaces.** Use hyphens: `second-brain`, `acme-renewal`, `START-HERE.md`. These names get typed into shells, passed to tools and synced between machines, and spaces or non-ASCII characters break that in ways that are miserable to debug. If they propose a name with spaces, explain why and offer the hyphenated form. Their **content** goes in whatever language they think in.

### Make it portable: the first card

Whether the folder keeps its own copy of this skill, in `<their folder>/.claude/skills/second-brain/`, is the owner's call, so it is not asked out loud and not left in chat: **it is the first card in `TASKS.md`**, a *decide* card, written at setup. It is also the first card they ever see, which makes it the example of what every card after it looks like.

- **A · keep a copy in the folder.** The folder carries its own rules, including `references/ROUTING.md`, and survives a dead laptop, a new machine and a different tool. The copy does not update itself; updating means pasting the install line again inside the folder.
- **B · no copy.** The folder relies on the skill installed on this computer, and updates whenever that does. On a new computer, the install line has to be pasted once.
- **Recommendation:** A if the folder syncs to a cloud drive or moves between machines; otherwise B.
- **If they do nothing:** B. Nothing is copied.

---

## WHAT APPEARS LATER — each thing on the day it is needed

| What appears | The day it appears |
|---|---|
| `areas/`, and the first area in it | the person names the first area, from material |
| `areas/<name>/notes/` | the first file filed into that area |
| `areas/<name>/INDEX.md` | roughly the fifth file in that area |
| `inbox/` | the first thing that has no area yet |
| `archive/` | the first time anything is retired |
| the *Done and cancelled* section of `TASKS.md` | the first card closed |
| the first line in section 7 of `CLAUDE.md` | the first rule for all their work, or for an area not yet born |

**None of these gets installed early "so it is ready."** A file that answers a question nobody has asked yet reads as an answer, and a reader cannot tell a placeholder from a decision.

---

## ORIENT — every session

Read, in this order: the root `CLAUDE.md` (loaded automatically; read it, do not skim it) → `BOARD.md` → `TASKS.md` → the `README.md` and `STATE.md` of the area in play.

That is the whole mandatory set, and it is deliberately small. **A reading list of twenty files gets skimmed, and a skimmed rulebook is no rulebook.** Nothing else in an area loads automatically; use its `INDEX.md` to find things rather than walking folders.

Open your first reply with one line, so the owner can tell at a glance that you read:

`area: <name> · read: BOARD, TASKS, <area>/STATE`

With no area in play: `area: — · read: BOARD, TASKS`. The session that ran BOOTSTRAP skips the line; it wrote the files it would have read.

**Then, before answering anything: is it already here?** Look for it in `TASKS.md` and `DECISIONS.md` first, and if it is there, say so before anything else: *"Already on your list since 14/10: Send Dana the Q1 numbers. Do it now?"* · *"You decided this on 02/10: «we only quote in shekels». Does it still hold?"* That one look is what stops the same task being written three times and the same question being decided twice, differently.

**Exemption:** an area that arrived carrying **its own rulebook** follows **its own opening protocol** when a session works inside it. ORIENT as written binds sessions working at the root or across areas.

---

## CAPTURE — the decision inside the sentence

**This is the part that makes the folder worth having.** Filing a document someone hands you is easy; they already know it matters. The expensive things are the ones said in passing, and nobody hands those over.

### A decision

**What it sounds like:** *"from now on…"*, *"we're going with…"*, *"let's not…"*, *"I told the client…"*, *"my manager decided…"*, *"fine, X it is."* In any language: listen for the shape, not the phrase.

In the same turn:

1. **A line in `DECISIONS.md`, at the end of the file**: the date · the area (*general* while no area fits) · what was decided · **the sentence that decided it, quoted, and whose sentence it is** · who decided (the person, their manager, a client, named) · why, **as it was given, or "not said"** · what it replaces, or "not said". When the decision is relayed (*"my manager decided…"*), quote the person's own sentence, say it was relayed, and name who decided; never put words in the decider's mouth. Never supply a reason nobody gave; an invented *why* is the most convincing false line a log can hold.
2. **If it binds future work, it also lands where it is applied.** A rule that belongs to one area goes in that area's `README.md` under *Rules here*. A rule for all their work, or one whose area does not exist yet, goes in section 7 of the root `CLAUDE.md`, *standing rules*, whoever set it; when its area is born, it moves into that area's README in the same action. Either way it points back to its log entry by date and title: `(DECISIONS, 2026-10-19: quotes in shekels only)`. **Nothing lives only in the log.** A rule that exists only in a history file is a rule no session will ever apply. **And the rulebook takes a rule only if a session that did not know it would do damage**; everything else is fine where it is.
3. **One line in chat, in their language**, even when the decision is also a rule: `Logged in DECISIONS, and added to the standing rules: «from now on we close at 21:00».` They can correct it while it is fresh. Talking to them, section 7 is *"the standing rules at the end of CLAUDE.md"*, never a section number.

**Thinking aloud is not a decision, and neither is a preference voiced once.** When you genuinely cannot tell, ask one line, *"Is that decided, or still open?"*, and if it is open it becomes a *decide* card. That question is worth its cost: a guess in either direction leaves a false line in the one file that is supposed to be permanent.

**A capture they correct in the same conversation is fixed in place.** It was your misreading, not their history. Anything older is never edited; it is reversed by a new line.

### Something to do, decide, approve, or wait for

**What it sounds like:** *"I need to send…"*, *"I have to decide whether…"*, *"I need to sign off on…"*, *"I'm still waiting for the numbers from…"*, *"remind me to…"*.

It becomes **a card in `TASKS.md`** in the same turn, and the chat gets one line: `Added a card: Send Dana the Q1 numbers.` Several at once means several cards and one line: *"3 new cards. The urgent one: …"*

**The test for every card: they read it on their phone, having read nothing else today, and can act on it.** If understanding it requires knowing what happened in this conversation, the card is not finished. That is why every card says what is happening in two or three plain lines, and why **a card's title is a verb and a thing, never an internal code.**

Four kinds, and the kind decides what the card must carry:

| Kind | Must carry |
|---|---|
| **decide** | the options, what each one means in practice, and your recommendation |
| **do** | what done looks like; and when the steps are known, the steps (where to go, what to click, the full text to paste) |
| **approve** | each thing to check, where to find it, and a separate answer for each one |
| **waiting** | who owes it, what exactly, since when, and the day to nudge |

And every card, whatever its kind, says **what happens if they do not act**: the default and when it takes effect, or "this blocks …". An open item with no recommendation and no default hands responsibility back instead of asking for a decision, and it is the reason lists like this stop being read.

**The due date, the urgency, what done looks like and the day to nudge are the owner's terms, not yours.** Write what they said. Where they said nothing: leave urgency out, write "not said" for done, and for a nudge day propose one, marked *proposed*, and say so in the chat line. A date you worked out keeps the word it came from: `2026-10-22 (Thursday)`. Cards are ordered by due date, earliest first, and cards with no date go last, unless the owner has put them in an order of their own.

**Cards and log entries carry no evidence / inferred / unknown labels; their fields do that job.** A quote is the evidence, *proposed* marks what you inferred, and *not said* marks what is unknown. The labels are for claims inside filed material.

**CAPTURE does not touch `BOARD.md`**, unless what was said changes where an area stands.

Three more rules, each from a real failure:

- **A card opens when it can be acted on.** Something that cannot start until something else is done is a line in the area's `STATE.md` (*"after the contract is signed: send the onboarding pack"*), not a card. A list full of things nobody can do yet teaches the person that the list is not for doing.
- **An answer closes its card in the same turn.** The card moves to *Done and cancelled* with the date and **what they said, in their words**. If the answer was a decision, it also gets its line in `DECISIONS.md`. **An answer that lives only in chat is lost the moment the next question arrives.** Measured on a real working project: five separate "waiting on you" lists, ninety-odd lines, most of them already settled, and the owner's words: *"it gives me tasks and I don't know what it's talking about… I ask about one and the others get lost."* One list of cards replaced all five.
- **Nothing that needs the person lives anywhere else.** Not in a report, not in an area's notes, not as a line at the bottom of a long answer. If it needs them, it is a card.

### Work for later that is not theirs

Something comes up mid-session that an agent could do, but not now: research a tool, map a spreadsheet before deciding what to build on it. In chat it gets lost; as a card it pollutes *waiting on me*, because there is nothing in it for the person to do. **It goes to the *For Claude, later* section of `TASKS.md`**: what to do, what the result is and where it goes, and the line to paste to start it. It never counts as waiting on them, and it never decides anything. What comes out of it is a file, and what to do with that file is theirs.

### A spec, a comparison, a piece of research

**Saved in a file, never left in chat.** It goes into the area's `notes/` in the same turn and is linked from the card or the `STATE.md` it feeds. The next session that needs it reads it instead of doing it again. (The owner's words, when this became a rule: *"it matters that all of these specs are saved, so we won't have to come back to them."*)

---

## INTAKE — "here, take this"

**This is where these systems actually die.** Not from bad content, but from good content filed where nobody will find it, at a trust level it never earned. Run the four questions in `references/ROUTING.md`, in order.

**Filing is not finished when the file exists:**

- the file's **header block** states `kind:` and `trust:`, directly under the title, above any content (not literally line one: the title is line one, and a rule written that way is broken by every file that has ever existed);
- **every claim inside it is labelled `evidence:` · `inferred:` · `unknown:`**, and `evidence:` names its source. Per claim, not per file, and unlabelled is a defect. Measured on a real install, an area produced about 244KB of research with inference written in the voice of finding; three of the claims everything rested on were guesses, and the owner could not learn anything from their own material. Use the owner's words for the three labels if the folder is not in English;
- a row in the area's `INDEX.md`, under a topic heading in the owner's words (create it from `area-INDEX.md` once the area passes about five files; it is the retrieval surface, so it is not optional once there is anything to retrieve);
- the area's `STATE.md` last-touched date;
- the `BOARD.md` row;
- a decision inside it → its line in `DECISIONS.md`. **A decision that arrives inside a working document is still a decision.** Extract it, or in six months someone decides it again, differently;
- something only the person can settle → a card;
- **and one line in chat saying where it went**: `Filed: areas/acme/notes/2026-10-19-pricing-call.md.` They should never have to ask.

Skipping the index or the state update is the real failure mode. The file exists and is invisible, which is worse than not having written it, because the person now believes it is handled.

**Unsure which area?** `inbox/`, with a line in the file's header saying what it is and why it was not placed. Never invent an area to hold one file. A wrong file in a right-looking place reads as *decided*; an honest unsorted one reads as *pending*.

**When an area is born** (the owner names one, or a cluster in `inbox/` turns out to be an area of their work), it gets `README.md` and `STATE.md` from `area-README.md` and `area-STATE.md`, **plus its row on `BOARD.md` in the same action.** If it is the first area, it creates `areas/` too, and the board's "no areas yet" line comes out in the same edit.

**Taking in a whole existing folder?** The test is simple: **does it have a live `.git`, or is anything actively writing to it?** If yes, make it a *pointer* area: a `README.md` and `STATE.md` saying where it lives and how to work with it, nothing copied, nothing moved. If no, make it a *contained* area: **copy, never move**, verify the copy before touching the original, then reconcile the roles it duplicates. **A contained take-in is not finished until the duplicate it created is closed**: hash every file both ways, account for every difference, rescue anything unique, then hand the decision over in one line (*"the original is now redundant: delete it, or keep it as a backup?"*). Never delete it unasked, and never leave the question unasked. The full procedure, and how to verify an import someone says already happened, is in `references/ROUTING.md`.

**Keep the index current, and let the area stay flat.** `notes/` holds everything; `kind:` and `trust:` sit in each file's header block. **People look for things by what they are about**, never by which stage of a process produced them, so `INDEX.md` grouped by topic, plus plain search over markdown, is what finds things. Folders are only storage. A sub-folder appears only when a topic passes about five rows in the index, and it is named exactly like the heading, in the owner's words.

**There are two valid ways to say trust, and an area uses one of them, never both.** An area this system creates uses the header label. **An area that arrived already sorted into `current/` · `needs-review/` · `completed/` keeps its folders**: re-cutting a working project to match the house style destroys the muscle memory of whoever built it. What is never allowed is one area using both, because then a file's trust has two answers.

---

## REVIEW — the part that cannot be skipped

Offer it when it is due. Never run one unasked. **The weekly review is due seven days after the last one**, and `BOARD.md` carries the date of the last one (at setup, the setup date). Each review writes its own date there when it finishes.

- **Weekly**: `TASKS.md`, end to end. What closed and what did not. **A card that has not moved for two weeks gets flagged**: twice is a signal, not laziness. Either it is not really theirs, it is too big to be one card, or nobody knows what done looks like. **Every *waiting* card past its nudge date gets named, with the days**: *"Dana, the Q1 numbers: 9 days."* Cards past their due date. `inbox/` emptied; early on, this is where areas get born. And every `assumed` line in `DECISIONS.md` confirmed or reversed.
- **Monthly**: scan `BOARD.md` for areas nobody touched, and report it **as data, flatly**: *"supplier X: 41 days."* Not "you have been neglecting supplier X". The person already knows how they feel about it; what they lack is the number. Offer the sweep alongside it.

### The board is status. It is never history.

**`BOARD.md` is the most expensive file in the folder, and it gets expensive quietly.** Every session reads it before doing anything, so whatever accumulates there is paid for again on every open. What accumulates is always the same thing: dated paragraphs, a second telling of what is already in `DECISIONS.md`. Measured on a real install, the board reached 26,888 bytes, and 84% of them were exactly that. By then the board contradicted itself: paragraphs at the bottom still described an area renamed nine days earlier, while the table above showed the current ones.

So **a paragraph on the board that opens with a date belongs in the log.** The board carries the table and one short paragraph of what is true *right now*, and stays under about 6KB. The same holds for an area's `STATE.md` (about 4KB) and for `TASKS.md`, whose *Done and cancelled* section moves whole to `archive/<date>-done-cards/` when the file grows past about 10KB.

**Cutting one is a four-step operation, and the first step is not optional:** copy the whole file verbatim into `archive/<date>-<what>/` **before touching it**; check each dated paragraph against the log; **write a log entry for anything that lived only there**; then rewrite. Say honestly in the log which check you ran: matching by date is not comparing sentence by sentence.

### The sweep

The reviews above are the owner's. This one is yours, and it exists because filing has steps that reliably get skipped. Offer it when a lot has arrived at once, or alongside the weekly review:

- cards past their due date, and *waiting* cards past their nudge date
- a card answered in chat and still open
- a decision sitting in a note, a card or a chat summary that never reached `DECISIONS.md`
- a standing rule that exists only in `DECISIONS.md`: nothing lives only in the log
- files no `INDEX.md` mentions: they exist and are invisible
- areas whose `STATE.md` date is older than their newest file
- **the same file living in two areas**, checking sizes and dates, not just names. A duplicate that has drifted is not clutter, it is a trap: the stale side reads as authoritative and carries no sign that it is dead
- **an item closed without its references repaired**: the counts, cross-references and notes that named it are now wrong, in files nobody re-reads
- links pointing at files that moved, **skipping `archive/`** and reporting its count separately. An archived document is a photograph of a moment; its dead links are evidence, and repairing them falsifies the record
- anything factual carrying no date
- **the same number or rule stated in two places.** Pick the home, and turn the other into a link
- **and contradictions inside single files**, not only across them. A document updated in one section and not another reads as authoritative either way

**Before you report "found nothing", run the same check on something you know is there.** A search that has not been shown to find anything is not a measurement. Measured on a real project: five checks in one night came back clean, and every one of them had missed a real defect, because the search could not see what it was looking for.

**Two things about how a sweep is allowed to act.** When the fix is "remove the duplicate", archiving is the easy half and the stub is the half that matters: move it to `archive/<date>-<what>/` and **leave a short file in its place** saying where the live version is and what happened. Otherwise the next session that goes looking finds nothing and writes a new one, which is how a duplicate comes back. And when a document describes something no longer true, **fixing the description is not deciding the question**: correct the statement of fact, and leave the open item open, saying so in the same breath.

Fix the mechanical parts and report them; leave anything that changes meaning to the owner. **Offer it, never schedule it.** A sweep on a timer bills for nights when nothing happened and trains the owner to stop reading its output.

### Before you say a long piece of work is done

**Re-read the original request, from the file or the message and not from your memory of it, and list everything it asked for.** Check each item against the folder. Do what is missing, then report. Long sessions lose things quietly, and the agent that did the work is the worst-placed to notice, because it remembers what it meant to do. (The owner, on adopting this: *"it finds and fixes mistakes and things that get missed in long runs."*)

---

## The laws

- **The owner defines the terms.** Never decide what "done", "urgent", "enough" or "good" means for someone. Build the surface where they write it down, then hold them to what they wrote. **Their capacity is one of those terms.** An ordinary working week is an assumption, not a fact; an alarm raised against an invented baseline costs more than no alarm, because it spends the one thing this system runs on, which is the owner still believing what it tells them. If it is not written down, ask.
- **Every decision goes in a file**, in the same turn, with the date, the words and who decided. Conversation memory does not survive the session.
- **Everything that needs the person is a card**, and every card passes the phone test.
- **Never delete, never overwrite.** Move to `archive/` with a date. `DECISIONS.md` is append-only: a reversed decision gets a new line that supersedes the old one. A finished or cancelled card is closed with its date and reason, never removed.
- **Never promote trust.** `needs-review` → `current` is the owner's call, always.
- **Never create an empty folder**, and a folder holding nothing but a README about itself is an empty folder.
- **No absolute paths, anywhere.** This folder gets renamed, moved and copied to other machines.
- **Check the source, not the summary.** A report saying "done" is not evidence. If you did not look, say you did not look. And "nothing found" means nothing until the search has found something you knew was there.
- **Owner unavailable?** Take the documented default, proceed, and log it `assumed`. Never block silently.
- **Names, not codes.** In everything the person reads and everything you say to them, things have names. An id is for agents, and it never appears in a card's title or in chat.
- **Quiet is not failure.** An area with nothing open can be perfectly healthy. Most of work is keeping things running.
- **An area is an area of work, never a category of files.** Material lives inside an area or in `archive/`; it never earns one of its own.
- **Someone else's material is not yours to hand around.** A client's documents, an employer's numbers, a colleague's message: nothing from one area goes into another, or out of the folder, without the person saying so, item by item. Access in one area never implies access in another.
- **Assume that if it can, it will.** Instructions are not a permission layer. Anything irreversible or outward-facing (sending, publishing, paying, deleting) is described on a card and done by the owner. Keep the keys outside.
- **Date every fact.** An undated number reads as current forever.
- **No secrets in the folder. Ever.** No passwords, API keys, tokens, account numbers or `.env` files, not in a note, not carried in with an imported folder, not "just for now". **Names, where a thing is managed, who has access, when it was last checked: all fine.** The values belong in a password manager. **Check for this at intake rather than trusting it**, because a real project brings its own. And once one has been in here, removing the file does not close it: a synced folder keeps it in version history. **Rotation is the only action that closes an exposed credential.**
- **A prohibition with no replacement gets filled by a guess.** An agent missing a detail does not stop; it fills the gap with the plausible thing and keeps building. **Every `never` written into this folder needs its `instead` next to it**, and the instead is usually *open a card and park the item until they answer*.

## Structure ceilings

**Max 3 levels below an area** · **max ~7 items in any one view, excluding tool files like `CLAUDE.md`** · **a sub-folder appears from the ~5th row under its topic heading in `INDEX.md`** · **zero empty folders**. The depth ceiling binds structure this system creates; **an imported area's own tree is exempt**, however deep it runs.

**Dot-directories are tools, not content.** `.obsidian/`, `.claude/`, `.git/` and their kind belong to whatever the owner uses to read, edit, sync or version the folder. They count against no ceiling, and they are never tidied away.

## One rulebook, one door

**Built for Claude Code, and the rulebook *is* the root `CLAUDE.md`.** There is no separate constitution file: the rules live in the one file Claude Code loads automatically for every session at or below the folder, so they cannot be skipped. A session opened inside an area still loads it, because the tool walks upward and loads every `CLAUDE.md` it passes, and the rulebook's first section sends it to that area's `README.md` and `STATE.md`. That is why an area this system creates needs no `CLAUDE.md` of its own.

Other tools read other filenames (`AGENTS.md`, `GEMINI.md`). **Do not install them.** If a second tool ever enters the picture, add a three-line pointer under that tool's name, aimed at `CLAUDE.md`, never a copy of the rules. Two rulebooks always drift. **An adapter is an address, not a home.**

### The same rule binds skills, and that is where it actually breaks

A folder like this accumulates skills of its own: a procedure the owner runs often enough to be worth packaging, living in `<folder>/.claude/skills/`. **A skill is a trigger and a procedure. It is never a second home for a rule.** Measured on a real install, a folder-local skill grew to 202 lines by restating the documents it pointed at, and two weeks later carried two contradictory targets for the same number, both dated the same day. The redundancy that was supposed to be a safety net was the thing that lied.

**The owner's own test settles what goes where:**

> *If there is any chance you would ever want to read it or fix it yourself, it is a document. If only an agent would ever execute it, it belongs in the skill.*

So a skill holds **when it wakes up** (its `description`), **what to read and in what order**, **the procedure nobody but the agent runs**, and **the shape of its output**. It holds no laws, no targets, no numbers and no restated rules. **One exception:** a rule whose violation harms someone *outside* the folder may be flagged in the skill by name, pointing at the document. A flag is an address; a summary is a second copy.

**The reason to keep a skill short is drift, not tokens.** Only its frontmatter `description` enters a session; the body loads when it triggers. Someone who believes they are saving tokens will trim the file once and let it grow straight back.
