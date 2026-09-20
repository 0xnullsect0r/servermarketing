# Questions I needed answered and could not answer myself

Facts I needed for the copy and did not have. I have written placeholders or
conservative wording rather than inventing anything, per the brief.

Ordered by how much the answer changes the work.

---

## Q1. Is anyone actually online during Pacific hours? `[VERIFY-1]`

**Why it matters:** this is the proposed headline differentiator, and not one
of the 43 competitors claims it. It is also the only claim in the plan that
could embarrass the server if it turns out to be false, because a New Zealand
player who joins expecting company and finds an empty world leaves
immediately and does not come back.

**What I know:** the owner says several friend-group members are in New
Zealand (UTC+12/13 against Pennsylvania's UTC-4/5). The MOTD already says
"International Server". The arithmetic is sound.

**What I do not know:** whether anyone is actually logged in at, say, 09:00
UTC on a Tuesday. Arithmetic is not observation.

**How to resolve:** seven days of hourly polling. Method, the exact cron
line, and how to read the result are in `assets/systems/tracking.md` §1.
Costs nothing and runs itself.

**Until then:** every affected line is marked `[VERIFY-1]` and has a fallback
written next to it.

---

## Q2. What do the existing 32 players actually value?

**Why it matters:** these are the only people who have already made the
decision this whole plan is trying to get strangers to make. Their reasons
are worth more than all of my competitor analysis.

**What I do not know:** why they stayed, what nearly made them leave, how
they found it, what they would tell a friend.

**How to resolve:** ask in the Discord. Four questions, no form, just a
message:

> Quick one for anyone who wants to answer: how did you find this server,
> what nearly made you not bother, what has kept you here, and how would you
> describe it to a friend in one sentence?

That last question is the valuable one. If several people describe it the
same way and it is not how `assets/core-messaging.md` describes it, **their
wording is right and mine is wrong.** Rewrite the messaging around it.

Cost: five minutes. This is the highest-value unanswered question here after
Q1.

---

## Q3. What is the real slot ceiling?

**Why it matters:** the cap is currently 20 against a stated ~32 players. A
new recruit who hits "Server full" on their first attempt is gone
permanently, and every listing renders `x/20`, which reads as a private
server.

**What I do not know:** how much RAM and CPU headroom the box has, and what
TPS looks like at 15 or 20 concurrent. Only the owner can judge this.

**How to resolve:** check the numbers, then set the cap to something above
the existing player base. Even 40 with a soft expectation of 15 concurrent is
better than a hard 20.

---

## Q4. Will the world ever be wiped? `[VERIFY-2]`

**Why it matters:** this is the single most persuasive thing this server
could say to its core segment. The directory has a "Last Reset" filter with
buckets from 7 days to 12 months, which means wiping is common enough to
need one, and one competitor puts "(No resets)" in its server name while
another advertises "Wiped 01.01.2026".

**What I do not know:** whether the owner will commit to never wiping.

**Why it needs an explicit decision:** a promise not to wipe that is later
broken is far more damaging than never making it. Do not publish this
because it sounds good.

**Fallback if he will not commit permanently:** *"No wipes planned, and if
that ever changes you will get a month's notice."* Still stronger than
anything the competitors say, and keeps the option open.

---

## Q5. What are the official ATM Discord's advertising rules?

**Why it matters:** 177,035 members, 59,120 online, and its own description
says people go there to find a server. By measurement it is worth more than
everything else in this plan combined.

**What I do not know:** whether it has a server-advertising channel, what it
is called, what the cooldown is, whether links or images are allowed.

**How to resolve:** join, find the channel, read the pins, read twenty recent
posts. Twenty minutes. Scheduled for Mon 28 Sep in `CALENDAR.md`.

I could not do this because I cannot join a Discord server.

---

## Q6. Is Planet Minecraft worth anything for a modded server?

**Why it matters:** it is a large site and it is the one general listing
venue I could not evaluate.

**What I do not know:** whether its modded/ATM presence is real. Cloudflare
blocked all my requests.

**My prior, clearly labelled as a guess:** it is builds-and-vanilla dominated
and belongs in tier 3 with the other general lists.

**How to resolve:** ten minutes. Search the site for "All the Mods" and see
whether anything real and recent comes back. If there are active ATM servers
with players, promote it to tier 2 in `assets/listings/listings.md`.

---

## Q7. Is this server 18+, or not?

**Why it matters:** `assets/reddit/04-minecraftbuddies-lfg.md` currently says
"18+ preferred, not strictly enforced", which is a hedge. A stated rule that
is not enforced is worse than no rule.

Worth noting: the one competitor with an explicit adults-only angle, "ATM10
for Grownies", sits at 0/20. The segment is recognised and nobody has served
it well, so there is room, but only if the rule is real.

**How to resolve:** owner decides. Either commit to 18+ and enforce it, or
drop the age framing entirely and describe the server's actual character
instead ("mostly people with jobs" is true, checkable, and does not require
enforcement).

---

## Q8. Is PvP on or off? Are there claims or protections?

**Why it matters:** both are standard listing fields and I had to leave them
blank. They also materially affect who the server suits.

**What I do not know:** the `server.properties` PvP setting, and whether any
land-claim or protection mod is in use.

**How to resolve:** check, then fill in the tag lists in
`assets/listings/listings.md` and add a line to `#start-here`. Two minutes.

---

## Q9. Disboard and top.gg specifics

**What I do not know:** the exact current listing rules and field limits.
Both blocked my requests, so the mechanics I describe in
`assets/discord/directory-listings.md` (2-hour bump cooldown, auto-bump
prohibited) are documented behaviour rather than something I read on the
page today.

**How to resolve:** read them when you create the listings. The copy will fit
regardless; only the field limits might need trimming.

---

## Q10. The specifics behind the claims the copy makes

Small things the copy asserts that I took from the brief and could not verify
myself. Confirm each before publishing, or soften it:

- **"Twice daily scheduled restarts with countdown warnings"**: what are the
  actual times, and what do the warnings say? The exact times should go on
  the website and in `#start-here`, because specificity is the point.
- **"Real backups"**: how often, retained how long, stored where, and has a
  restore actually been tested? "Backups I have restored from" is a much
  stronger claim than "backups" and it should only be made if true.
- **How long has the server been running?** Uptime history is among the
  strongest evidence for the durability positioning and I do not have a
  start date. "Running since [month]" belongs in every pitch.
- **What mods and blocks built the spawn?** Needed for
  `assets/reddit/02-allthemods-build.md`. A vague answer there reads as
  someone who did not build it.
- **Is the world pre-generated, and to what radius?** Needed for the
  r/admincraft post, and it is a genuinely persuasive detail for Segment C.
