# OWNERSHIP — who owns what, and where it runs

> **Created: << YYYY-MM-DD >>.** One map for every activity in this folder: whose business it is, who owns the IP, what the owner's role in it is, and where the infrastructure actually lives.
> **This file appears the day a second party enters the folder** — a branch serving someone else's business, someone else's product, or someone else's money — and not before. Until then it is a one-row table saying "mine", which is worse than no file at all.
>
> 🔒 **Names, ownership, where a thing is managed, who has access, and when that was last checked — yes. The value of a key, password or token — never, in any row.** This folder syncs to a cloud drive and is read by agents; it is the wrong shape for anything whose entire value is that nobody else holds it. The values live in a password manager, outside this folder.
> **Every field carries the date it was true.** A field with no date counts as unverified, never as current.
> **`?` means nobody has decided.** That is not a gap in the documentation — it is a live item in `decisions/OPEN.md`, and it gets a link.

---

## 0. The order, in the owner's words

> << their sentence: which activity is *the* business, and which are side income >>

<< A quotation, with its date. Never an agent's summary of one, and never an agent's inference from where the hours go.
   This section exists because it is the only thing in the folder that settles an argument between two activities —
   and until the owner has actually said it, this section says exactly that and links to the open item. >>

**The capacity this order rests on, in their words:** << hours, shape of the day, with the date >>.

<< Written down because the alternative has been measured: an agent reached for an ordinary working week, called a
   commitment "most of the week", and was corrected by the owner — the real week was far longer and the commitment was
   about a third of it. An alarm raised against an invented baseline costs more than no alarm, because it spends the one
   thing this system runs on, which is the owner still believing what it tells them. If capacity is not written here,
   an agent asks. It does not assume. >>

## 1. Commercial ownership

| Activity | Whose business | Who owns the IP | The owner's role | How the owner gets paid | As of |
|---|---|---|---|---|---|
| << name >> | << the owner · someone else, named >> | << >> | << builder · employee · partner · paid contractor >> | << the mechanism, or `?` with a link to the open item >> | << YYYY-MM-DD >> |

## 2. Infrastructure — one table per activity

### << activity >>

| Component | What | As of |
|---|---|---|
| repository | << where the code lives, and **under whose account** >> | << YYYY-MM-DD >> |
| hosting | << >> | << YYYY-MM-DD >> |
| database | << >> | << YYYY-MM-DD >> |
| cloud / identity | << >> | << YYYY-MM-DD >> |
| automations | << >> | << YYYY-MM-DD >> |
| who has access | << named people, and how they sign in >> | << YYYY-MM-DD >> |
| what it costs | << who pays, how much, or "nothing" >> | << YYYY-MM-DD >> |

<< **Under whose account** is the column that matters and the one everybody leaves out. Someone else's product running
   entirely on the owner's accounts is a completely normal arrangement and an expensive surprise: it belongs on the
   record while everyone is still friendly, not on the day it ends.
   An activity that has been agreed but not yet handed over gets a table too, with one honest row saying so. "Nothing
   has arrived yet" is a fact about the engagement, and a missing table reads as an oversight. >>

### << an activity where nothing has been handed over yet >>

| Component | What | As of |
|---|---|---|
| everything | **Not handed over. No access, no repository, no credentials.** | << YYYY-MM-DD >> |
| the rule | 🔒 **No key belonging to another party ever enters this folder.** Not once, not temporarily. | << YYYY-MM-DD >> |

## 3. Rules that follow from this map

- **A branch that is not the owner's is not the owner's to hand around.** Nothing from it goes to any other party without the owner saying so, per item — and "any other party" includes the people in another branch.
- **Access in one activity never implies access in another**, even when the same person appears in both.
- **The same person can appear in two activities in different roles, and when that happens nothing about it is neutral any more** — which one gets the hours when both break on the same day, what a rate conversation costs, what an assumption about access is worth. Write the overlap down as a fact on this map. It does not resolve itself by being obvious.
- **Anything not written here is not agreed**, however clearly it was said out loud. Where there is no contract, this file is the entire memory of what was agreed — so a change in rate, scope, or what is included gets its line here on the day it is said, with the date. This is not a substitute for an agreement. It is what exists instead of one.
- **An intention carrying no date and no trigger changes nothing.** "I'll reduce this later" is not a plan; the thing to track is the reduction, and it needs an item in `decisions/OPEN.md` with a date on it.
- **This map is confirmed at the quarterly review.** Every field that has gone a quarter without confirmation is re-dated against reality or marked `?`. A document that declares itself the source of truth is not one — measured here: a file with exactly that claim in its opening line sat a month stale while being quoted as current.
