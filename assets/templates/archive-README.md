# archive — retired

**Things arrive here only by explicit decision. Never by deletion.**

## Why this matters so much here

Most installs have no version control. **What is deleted is gone** — no history, no recovery, no way to ask what used to be here.

So:

- **Nothing is deleted.** It moves here, with a date in the folder name.
- **Nothing is overwritten.** A replaced file moves here first; the new one is written afterwards.
- Every move gets a line in [decisions/DECISIONS.md](../decisions/DECISIONS.md) with the reason.

## Shape

`archive/<< YYYY-MM-DD >>-<< what it was >>/`

The date is **when it was retired**, not when it was written. Someone searching here in two years is asking "when did this stop being true", not "when was this created".

## The second safety net

If this folder syncs to a cloud drive, that service's version history and recycle bin are the real undo for an accidental deletion. **Worth confirming once that they are actually switched on** rather than assuming it.

---

## Links inside archived folders are expected to be dead

**Do not repair them.** An archived document is a photograph of a moment. Its links pointed at the world as it was, and rewriting them to resolve today would quietly falsify the record — the file would then claim to describe a state that never existed.

**A link check on this folder skips `archive/` and reports its count separately.** That is what "historical context only" means in practice, and it is the difference between a broken link that is a defect and one that is evidence.
