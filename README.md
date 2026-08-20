# second-brain

**Turn one empty folder into a second brain — and keep it usable for years.**

A folder that holds a whole life. Every area is a *branch*: work, money, health, family, a course you're building, whatever you actually have. No preset list, no limit. Built for **Claude Code**: the rules live in the one file it loads automatically, so every session — any machine, no prior context — knows who you are, what matters, and where everything lives. The files themselves are plain markdown any tool can read.

Plain markdown files. No app, no database, no subscription, no lock-in.

---

## Install

Make a folder — **English name, no spaces** — open Claude Code inside it, and paste this:

```
Install the skill from https://github.com/idan-tec/second-brain into ~/.claude/skills/second-brain,
then set up a life-management system for me here.
```

That's the whole setup. The agent downloads it, installs it, and builds the folder in one turn — **asking at most one question: which language you think in.** Then you start throwing things at it.

Ran it inside a folder that already has files? **It won't touch them.** It builds into a fresh `second-brain/` sub-folder instead, and your existing files stay exactly where they are — you can feed them in later, deliberately, one at a time.

To update later, paste the same line again.

*(Prefer to do it by hand? Copy this repo's contents to `~/.claude/skills/second-brain/`. On Windows that's `C:\Users\<you>\.claude\skills\second-brain\`. Create the folder if it isn't there.)*

## What gets built

```
CLAUDE.md                the rulebook — loads by itself in every session; you never have to read it
START-HERE.md            the one file a human opens
BOARD.md                 one screen: every branch, its state, what you're neglecting
decisions/               what was decided and why · what's waiting on you
system/                  where things go · who wins when two things disagree
branches/                one per area of your life
inbox/  archive/         unsorted · retired, never deleted
```

No `compass/` at setup, and no empty folders anywhere. Goals get offered later, once there's enough here to have an opinion about.

**It grows into more than that, on triggers rather than on setup.** A branch gets an index around its fifth file, its own list of open questions with the first one that's genuinely branch-only, its own `archive/` the first time something there is retired. And the day a branch stops being yours — someone else's product you're paid to build, a relative's business running on your accounts — the folder grows a `system/OWNERSHIP.md`: whose business each branch is, who owns the IP, where every repo, database and automation actually lives, every field dated. **None of it is built in advance.** A file answering a question nobody asked yet reads as an answer.

## The ideas it's built on

**Three axes, not one.** Most systems sort by topic and stop. This one also tracks **how far something is trusted** (approved · unreviewed · finished · replaced) and **how sensitive it is** — because six months on, a draft and a locked decision look identical, and that's how false things quietly become true.

**Goals live only at the root, capped at five across your whole life** — and so does *this week*. Give every area its own goals and you can never choose *between* areas; give every area its own `NOW` and you have four things that are all urgent and nothing that chooses. Choosing between areas is the entire problem.

**Folders are storage; the index is how things are found.** People look for things by what they're *about*, never by which stage of a process produced them. So `notes/` stays flat and `INDEX.md` does the work.

**A branch is an area of a life, never a category of files.** Backups, invoices, screenshots and exports are material — they live inside a branch. Only a life area earns one, and only you name it.

**Nothing is deleted or overwritten.** Most installs have no version control, so `decisions/DECISIONS.md` is the entire memory. It's append-only.

**Maintenance is not failure.** A branch with no goal can be perfectly healthy. Most of a life is maintenance, and a system that only tracks goals makes it invisible right up until it fails.

## Using it

Throw material at it — a note, a link, a document, a whole folder — and it gets filed: right branch, right trust level, indexed so it can be found again. Knowing where things go isn't your job.

Ask it what you're neglecting. Ask for the weekly review. **Without the review this is a folder of dead files within six weeks — that part isn't optional.**

## What it won't do

It won't send, publish, pay, or delete on your behalf. Instructions aren't a permission layer: assume that if an agent *can* do something irreversible, one day it will, on a misread. Keep the keys outside the folder.

It holds no secrets. No passwords, no API keys, no `.env` files — and least of all somebody else's. Names, ownership, where a thing is managed and who can reach it — fine. The values belong in a password manager, outside the folder.

## Works with

Anything that reads markdown. Point **Obsidian** at the folder and it becomes a vault with a working link graph — nothing to convert. Sync with OneDrive, Dropbox, iCloud, or nothing at all. **git is optional and always will be**; requiring it would exclude most of the people this is for.

---

MIT licensed. Built in the open — issues and improvements welcome.
