# second-brain

**One folder that remembers your work for you: what you decided, what is waiting on you, and what you are waiting for from others.**

You talk to Claude about your work the way you would to a colleague. When you decide something, it goes in the log, in your words. When you mention something you have to do, decide, approve or chase, it becomes a card. When you hand over a note or a document, it gets filed where you will find it again. **You never have to know where things go**, and every time something is written down, Claude tells you in one line where it went.

Built for **Claude Code**: the rules live in the one file it loads automatically, so every session (any machine, no prior context) knows what you decided and what is open. The files themselves are plain markdown. No app, no database, no subscription, no lock-in.

---

## Install

Make a folder (**English name, no spaces**), open Claude Code inside it, and paste this:

```
Install the skill from https://github.com/idan-tec/second-brain into ~/.claude/skills/second-brain,
then set up a second brain for my work here.
```

That's the whole setup. The agent downloads the skill, installs it, and builds the folder in one turn, **asking at most one question: which language you think in.** You'll find one card waiting: whether the folder should keep its own copy of the rules. Ignore it and nothing is copied. Then you start talking to it.

Ran it inside a folder that already has files? **It won't touch them.** It builds into a fresh `second-brain/` sub-folder instead, and your existing files stay exactly where they are. You can feed them in later, deliberately, one at a time.

To update later, paste the same line again.

*(Prefer to do it by hand? Copy this repo's contents to `~/.claude/skills/second-brain/`. On Windows that's `C:\Users\<you>\.claude\skills\second-brain\`.)*

## What gets built

```
CLAUDE.md        the rulebook: loads by itself in every session; you never have to read it
START-HERE.md    the one file a human opens
TASKS.md         what is waiting on you: one list, every item a card
DECISIONS.md     what was decided, when, by whom, in whose words
BOARD.md         one screen: every area of your work and when it was last touched
```

**Five files, and not one folder.** Folders appear on the day they have something to hold: `areas/` with the first area of your work you name (a client, a project, a team, a process you run), `inbox/` with the first thing that has no area yet, `archive/` the first time something is retired. A folder created in advance just sits there empty, and an empty structure hides things instead of holding them.

## The ideas it's built on

**One list of what's waiting on you.** Not a list per project, not a line at the bottom of a long answer, not "I mentioned it earlier in the chat". Every card has to pass one test: you read it on your phone, having read nothing else today, and you can act on it. So it says what is happening, what your options are and what Claude recommends, and what happens if you do nothing.

**Four kinds of card**: something to **decide**, to **do**, to **approve**, or something you are **waiting for** from someone, with the day to nudge them.

**Decisions in your words.** The log quotes the sentence that decided it and says who decided: you, your manager, a client. A paraphrase reads, six months later, like a decision nobody made. And a decision that binds future work also lands where it is applied, so it does not live only in a history file nobody rereads.

**Before answering, Claude checks what's already there.** "That's already on your list since Tuesday" beats a third copy of the same task. "You decided this on the 2nd: does it still hold?" beats deciding it twice, differently.

**Folders are storage; the index is how things are found.** People look for things by what they are *about*, never by which stage of a process produced them.

**Nothing is deleted or overwritten.** The decision log is append-only, and a closed card stays closed with its date and your answer.

## Using it

Just work. Say what you decided, what you need to do, what you are waiting for. Hand over notes and documents. Ask "what's waiting on me?", "what did we decide about the supplier?", "where is the pricing doc?".

Ask for the weekly review. **Without it, this is a folder of dead files within six weeks. That part isn't optional.**

## What it won't do

It won't send, publish, pay or delete on your behalf. Anything like that becomes a card for you to do. Instructions aren't a permission layer: assume that if an agent *can* do something irreversible, one day it will, on a misread. Keep the keys outside the folder.

It holds no secrets. No passwords, no API keys, no `.env` files. Names, where a thing is managed and who can reach it: fine. The values belong in a password manager.

It is not a project manager or a goal tracker. There are no goals, plans or visions in here. It keeps the part of work that otherwise lives only in your head.

## Works with

Anything that reads markdown. Point **Obsidian** at the folder and it becomes a vault with a working link graph. Sync with OneDrive, Dropbox, iCloud, or nothing at all. **git is optional and always will be.**

## What changed in 0.3

Work only. The goal-setting part (`compass/`: who I am, horizon, season, this week) is gone, and so are life areas. The many "waiting on you" lists became one list of cards. Capturing decisions and tasks from conversation is now the core of the skill, not a side effect of filing. And a fresh install creates no folders at all: `decisions/`, `system/`, `inbox/` and `archive/` used to be created on day one and mostly sat empty.

---

MIT licensed. Built in the open; issues and improvements welcome.
