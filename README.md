# Free-channel growth plan for an ATM10 server

Research, strategy and finished copy for growing `mc.nullsect0r.dev` through
free channels. Written 2026-09-20.

---

# The three things to do this week

Everything else in this repo can wait. These cannot, because each one
silently cancels out effort spent anywhere else.

## 1. Decide the ATM10 version question. (Monday, 60 minutes)

**The server runs 7.1. CurseForge ships 8.1.** Four releases and just under
three months apart. Anyone who reads a post, installs the pack and clicks
connect gets 8.1, fails to join, assumes the server is dead, and leaves
without telling you.

Every post, listing and invite in this repo drives traffic into that wall.
**Fixing the wall is worth more than doubling the traffic.**

Three defensible options, laid out in `BLOCKERS.md` item 2: update to 8.1,
stay on 7.1 and say so loudly in every public asset, or announce a date and
recruit against it. All three are fine. The current state, staying on 7.1
without saying so, is the only bad one.

Most of the copy in `assets/` has a `[VERSION]` placeholder waiting on this.

## 2. Fix the Discord front door. (Tuesday, 30 minutes)

Right now a stranger clicking your invite sees a server called **"Homies"**
with **no icon**, **no description**, and lands in **`#general`** in the
middle of a conversation between people who know each other. Nothing tells
them what the server is, what version to install, or how to join.

Thirty minutes fixes all of it:

- Set a server icon (blank right now, so every embed renders a grey circle,
  which reads as abandoned)
- Set the server description
- Enable the server widget (one toggle, lets directories show "9 online")
- Create `#start-here` and pin the copy from
  `assets/discord/structure.md`, which is written and ready to paste
- Repoint the invite to land there instead of `#general`

Unlike a post, this works on every visitor forever.

## 3. Start the clock on the one claim worth building on. (Wednesday, 45 min)

The most distinctive thing about this server is that it has US and New
Zealand players, so it plausibly has people online when a single-region
server is empty. **Not one of the 43 competitors I catalogued claims this.**

It is also not yet verified. Paste the cron job from
`assets/systems/tracking.md` §1 and let it poll the status API hourly for
seven days. It costs nothing and it runs itself. In a week you will know
whether the claim is true, and several pieces of copy are waiting on the
answer.

While you are at it, **take the spawn screenshots** (`assets/content/ideas.md`
idea 1, two hours, shot list included). Six other deliverables are blocked on
having them, and the custom spawn is the best unexploited asset here.

---

**Do not post anything this week.** Week 1 in `CALENDAR.md` deliberately has
no posting in it. If only one week of this plan happens, make it this one.

---

# What is in here

```
README.md         you are here
STRATEGY.md       positioning, segments, channel ranking, honest assessment
CALENDAR.md       90-day schedule, 21 Sep to 19 Dec, specific enough to follow
QUESTIONS.md      10 facts I needed and did not have
BLOCKERS.md       5 things needing owner action or access I lacked
research/         findings, one file per area, sources and commands cited
assets/           all finished copy, organised by channel
```

## research/

| File | What is in it |
|---|---|
| `00-method-and-limits.md` | What I could and could not reach, and what that cost. **Read this before trusting anything else.** |
| `product-audit.md` | **The most important file.** Eight findings from pinging the actual server. |
| `competitors.md` | 43 public ATM10 servers, with a table and what the shape of the data means |
| `audience.md` | Who plays this pack, measured figures versus defensible inference |
| `channels-reddit.md` | Per-subreddit notes plus the verification checklist |
| `channels-server-lists.md` | The test showing general lists are a waste of time here |
| `channels-discord.md` | Why Discord is the top channel, with the numbers |
| `channels-content.md` | Short-form video, modpack platforms, and the underused channel |

## assets/

| File | What is in it |
|---|---|
| `core-messaging.md` | One-line, 50-word and 200-word pitches; ranked differentiators; the naming decision |
| `reddit/` | Six post drafts, one per subreddit, plus the comment engagement guide |
| `listings/listings.md` | Listing copy at three lengths, tags, which sites and in what order |
| `discord/structure.md` | Full Discord structure, roles, onboarding, and all the copy |
| `discord/atm-discord-post.md` | The highest-value single post in the plan |
| `discord/directory-listings.md` | Disboard and friends, and why not to build a bumping habit |
| `content/ideas.md` | Ten content ideas with effort estimates; three worked out fully |
| `website-spec.md` | Spec for a small status page |
| `systems/tracking.md` | Three metrics, free tools, and the seven-day measurement |
| `templates/templates.md` | Things you will write more than once |

---

# How to use this

**If you have ten minutes:** read the three things above, then
`research/product-audit.md`.

**If you have an hour:** add `STRATEGY.md`, particularly section 4, which is
the honest assessment of what will not work.

**If you are about to post something:** find it in `assets/`, check whether it
has a `[VERSION]` placeholder or a `[VERIFY-1]` / `[VERIFY-2]` marker, and
resolve those first. Then check the rules yourself. `BLOCKERS.md` item 1
explains why that last step is not optional.

**Create a `LOG.md`** at the top level the first time you post something.
Format is in `assets/systems/tracking.md` §4.

---

# Five things worth knowing before you read the rest

**The biggest problems are product problems, not distribution problems.** The
version gap, the "Homies" branding on every public surface, the 20-slot cap
against 32 players, and a status API that reports the server offline. Roughly
three hours of work, and worth more than the other twelve weeks combined.

**One Discord matters more than everything else put together.** The official
All The Mods Discord has 177,035 members and 59,120 online, and its own
description says people go there to find a server. For comparison, all 43
public ATM10 servers added together have about 600 concurrent players.

**The general server lists are not worth doing, and I tested that rather than
assuming it.** Their "Modded" categories contain 0 to 1 mentions of All the
Mods against 2 to 34 mentions of Cobblemon. Evidence in
`research/channels-server-lists.md`. One directory is worth doing; five are
not.

**I could not access Reddit at all.** Every route was blocked. The Reddit
drafts are conservative and clearly separate measured fact from inference,
and each ships with a rule-verification checklist. Ten minutes of your time
converts my inference into fact. Please do it before posting.

**Realistic outcome, stated up front so success is recognisable.** If all of
this is executed well, expect something like 10 to 25 people trying the
server over 90 days and 3 to 8 becoming regulars. That would roughly double
the active core and put this server third or fourth in the entire public
ATM10 category by average concurrency. It is also a long way from a full
server, and no free plan gets there. Reasoning in `STRATEGY.md` section 4.
