# TRUTH — who wins when two things disagree

> Any system that lives long enough contradicts itself. The question was never whether — only whether there is a written answer for **who wins**. This is that answer.

## Order of authority, highest first

### 1. An explicit, recent decision by the owner

Sets direction. A new decision beats any older document, including this one. **It has to be written into `decisions/DECISIONS.md` the moment it is made** — an unrecorded decision carries no authority here, because nobody can check it later, and "I'm sure we decided this" is not something a system can act on.

### 2. Verified reality

What is actually true right now, checked directly. Reality settles **what is**. It does not settle **what should be**.

> **Check the source, never the summary.** A report saying "done" is not evidence — the file, the account, the calendar, the actual state is. This single rule catches more errors than the rest of this document combined. It also only works if the source was kept: an extraction that discarded what it came from cannot be checked by anyone, ever, and quietly becomes the truth by default.

**And check the date.** A figure that was accurate when written is not evidence of anything today. If a line carries no date, treat it as unverified rather than current — that is usually the honest reading.

### 3. `compass/`, in its own order

`WHO-I-AM.md` > `HORIZON.md` > `SEASON.md` > `NOW.md`.

A task in NOW that contradicts WHO-I-AM is not a scheduling problem. It is a sign the task should not exist.

### 4. A branch's `trust: current` material

Authoritative inside its own branch, never outside it.

### 5. `trust: completed`

Evidence of what happened — useful for reconstruction and audit. **Not an instruction for today.**

### 6. `trust: needs-review`

May be right, partial, or stale. **Never presented as fact before review.** Quoting one of these without saying so is the most common way a false thing quietly becomes true — and since trust is a label on the file rather than a folder it sits in, **read the header block before you quote anything.**

### 7. `trust: superseded` and `archive/`

Historical context, and only when explicitly asked for.

## Resolution

| The question | What settles it |
|---|---|
| What is true right now? | Verified reality (2) |
| What should happen? | The owner's latest decision (1) |
| What happened before? | `completed/` and `DECISIONS.md` (5) |
| Reality and intent disagree? | **Neither.** Record the gap in `decisions/OPEN.md`. |

## Three things an agent must not do

1. **Never guess to close a gap.** An unverifiable claim is marked unverified and moved to `OPEN.md`. Presenting a guess as fact is the worst available failure here, because this folder *is* the owner's memory — a wrong entry does not just mislead, it overwrites what they would otherwise have remembered.
2. **Never promote trust unilaterally.** `needs-review` → `current` is the owner's, always.
3. **Never let a summary stand in for the source.** If you did not look, say you did not look.

## When the owner is unavailable

Take the documented default, proceed, log it in `DECISIONS.md` as `assumed`. Every `assumed` line is reviewed at the quarterly. **Never block silently, and never stall waiting for an answer that could have had a default.**
