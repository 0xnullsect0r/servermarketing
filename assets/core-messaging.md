# Core messaging

Everything in this file is written to be true of this server as measured on
2026-09-20. Two claims are marked **[VERIFY]** and must not be used publicly
until the owner has confirmed them. They are flagged inline.

---

## The naming question, which has to be settled first

Nothing else in this file can be finalised until this is. The problem is in
`research/product-audit.md` Finding 2: the Discord is called "Homies", the
MOTD says "Homies' International Server", and to a stranger evaluating where
to spend fifty hours, that reads as a closed friend group they will be
peripheral to.

This is not a criticism of the name. It is a good name for what it is. The
issue is only that it is doing public-facing work it was not designed for.

**Three options, with the case for each:**

**Option 1: Keep "Homies", lean into it, explain it immediately.**
The name stays. Every public asset opens by defusing it: *"It's called Homies
because it started as a group of friends. It isn't only that any more, and
you will not be the odd one out."* Cost: one sentence of every pitch spent on
defence. Benefit: nothing changes internally, no migration, no confusion for
existing players. **This is the lowest-effort option and it is a legitimate
choice.**

**Option 2: "Homies' International" as the public name.** Recommended. Keep
the continuity and the affection in "Homies", but pair it with the word that
turns a private-sounding name into a description of what makes the server
unusual. It is already half-done: the MOTD says exactly this. The change is to
use it consistently as *the name* across the Discord, the listing, and every
post, rather than burying it in the second half of an MOTD line. Cost: about
twenty minutes of renaming. Benefit: the name starts carrying the positioning
instead of working against it. **[VERIFY]** the international claim before
leaning on it, see below.

**Option 3: A new public name entirely.** Cleanest signal to strangers, but it
costs the existing community's sense of identity, confuses the ~49 people
already there, and orphans whatever history exists. I do not recommend it. The
problem does not justify the cost.

**Recommendation: Option 2**, falling back to Option 1 if the timezone data
does not hold up. All copy below is written for Option 2 with the Option 1
variant given where the wording changes.

---

## The [VERIFY] items

**[VERIFY-1] Pacific-hours coverage.** Copy below says there are usually people
online outside US evening hours. This follows from having New Zealand players
(UTC+12/13 against Pennsylvania's UTC-4/5), but it is arithmetic, not
observation. Run the seven-day measurement in `assets/systems/tracking.md`
first. If it holds, use the strong wording. If it does not, use the honest
fallback given with each pitch.

**[VERIFY-2] The wipe/reset position.** Several pitches below say the world is
not wiped. That is the single most persuasive thing this server could say to
its core segment (`research/competitors.md`, point 5), and I have written it
because the brief describes a persistent server with real backups. **The owner
must confirm he is actually willing to commit to it before it is published.**
A promise not to wipe that is later broken is far more damaging than never
making it. If he is not willing to commit permanently, the honest version is
*"no wipes planned, and if that ever changes you will get a month's notice"*,
which is still stronger than anything the competitors say.

---

## One-line pitch

Primary:

> A small All the Mods 10 server run by a software engineer on a dedicated box
> in Pennsylvania, with players in the US and New Zealand so it is rarely empty.

Shorter, for tight fields and Discord status:

> Small ATM10 server, properly run, players in two hemispheres, nothing to buy.

If **[VERIFY-1]** fails:

> A small All the Mods 10 server run by a software engineer on a dedicated box
> in Pennsylvania. Scheduled restarts, real backups, nothing to buy.

---

## Fifty-word pitch

Exactly 50 words:

> Homies' International is a small All the Mods 10 server on a dedicated box in
> a Pennsylvania datacenter. Players in the US and New Zealand, so someone is
> usually on. Twice-daily restarts with warnings, real backups, no
> store, no ranks for sale. Run by a software engineer who fixes things.

If **[VERIFY-1]** fails, swap sentence two for: *"Restarts are scheduled and
announced, backups are real, and the world is not wiped."*

---

## Two-hundred-word pitch

193 words:

> Homies' International is an All the Mods 10 server for adults who want their
> base to still be there in six months.
>
> It is small on purpose. Twenty to thirty people, most of whom recognise each
> other. Half of us are a group of friends, several in New Zealand, and half
> are people who turned up on their own and stayed. The practical effect of
> that split is that there is usually someone online at hours when a
> single-region server is dead.
>
> It runs on a dedicated box in a Pennsylvania datacenter, not a home PC and
> not a shared host. It restarts twice a day on a schedule, with countdown
> warnings so nothing is lost. Backups are real and tested. The world is not
> wiped.
>
> There is no store. No ranks, no crates, no keys, nothing to buy, and no plans
> to add any. The server costs what it costs and that is not your problem.
>
> It is run by one person who writes software for a living. When something
> breaks, you report it to the person who can actually fix it, and it gets
> fixed. That is most of the pitch.

If **[VERIFY-1]** fails, cut "several in New Zealand" to "in a few different
timezones" and delete the sentence about single-region servers.

---

## Differentiators, ranked by how compelling they actually are

Ranked by what the core segment, a returning ATM player whose last server
died, will actually care about. Not by what is most flattering.

**1. It is not going to disappear, and here is the evidence.**
The strongest thing this server has, because it answers the question the
audience is actually asking. Eleven of 43 listed ATM10 servers were offline
when I checked and about thirty average two players or fewer
(`research/competitors.md`). Everyone shopping has been burned. The evidence
to cite: a dedicated box on real transit rather than someone's spare PC, a
scheduled restart regime that someone clearly set up deliberately, tested
backups, and an owner with a professional stake in it working.
*Nearly every competitor ignores this entirely.*

**2. One competent owner who will actually fix your problem.**
On a large network, a bug report goes into a ticket queue staffed by
volunteers. Here it goes to the person with root who does this professionally.
This is concrete, verifiable within a day of joining, and impossible for the
big two to match. It is also the differentiator most likely to be *felt*
rather than just read, which makes it a retention asset and not only an
acquisition one.

**3. Coverage outside one region's evening. [VERIFY-1]**
Potentially the most distinctive claim available, because not one of the 43
competitors makes it. The competitor set segments by exclusion, `[EU]`,
`LATAM`, `CZ/SK`, `GER/ENG`, `PT`. Nobody sells coverage *across* regions.
Ranked third only because it is unverified. If the measurement holds, it moves
to first, because it is both unique and directly useful to Segment B.

**4. No store, and no possibility of one.**
Ranked deliberately low. "No P2W" is near-universal among ATM servers and
appears in two competitor names, so as a claim it signals almost nothing
(`research/competitors.md`, point 3). It becomes meaningful only in a
specific form: *there is no store, there is no donation tier, there is no
plan to add one, and the reason is that the box is already paid for.* That
version is a statement about structure rather than intent, and structure is
what a skeptical reader believes.

**5. Small by design, with actual numbers.**
"Small community" is another phrase every competitor uses. Saying "twenty to
thirty people and most of us recognise each other" is the same claim made
falsifiable, which is the only version worth making.

**6. A custom spawn that someone actually built.**
Floating island, central tower, elytra course, heavy modded blockwork. Ranked
sixth as a *claim*, because every server says its spawn is nice. It moves to
roughly second as an *image*, because a photograph is evidence and the
competitor set is competing purely in adjectives. Get the screenshots
(`assets/content/ideas.md`), then let them do this work silently.

**7. Pennsylvania datacenter hosting.**
True and verifiable (`23.161.184.9` geolocates to Sanatoga, PA, on Zayo
Bandwidth). Good ping for US East. Ranked last because it only matters to
players for whom it is true, and it is better deployed as supporting evidence
for differentiator 1 than as a headline.

### Not differentiators, do not use

- "Friendly" / "chill" / "welcoming" / "great community". Used by most of the
  43. Zero information.
- "Fun". Same.
- "Active staff". Meaningless at this size; "one owner" is more honest and
  more convincing.
- "Lag free". Nobody believes it, and on ATM10 it is a claim that invites
  someone to disprove it within an hour.

---

## The one-liner for existing players to forward

Segment D is the highest-converting audience in the plan and it only needs
something forwardable. Copy-paste, for the owner to post in the Discord:

> If anyone has a friend who used to play ATM and is looking for a server:
> we have room. Small, no store, dedicated box, runs properly, and we are on
> at weird hours because half of us are in New Zealand. Send them
> https://discord.gg/r84QJJgUCt and tell them to ask for me.

---

## Words to avoid everywhere

The audience is technical modded players with a good detector for
advertising. These are the tells:

- Exclamation marks in a pitch. One is a lot.
- "Join our community today"
- "What are you waiting for"
- Emoji bullet lists in a Reddit post body. Fine in Discord, wrong on Reddit.
- "Endless possibilities", "unforgettable experience", "like no other"
- Stacked bracket tags in prose: `[SMP] [Modded] [No P2W] [Friendly]`. Correct
  in a subreddit title that mandates the format, wrong anywhere else.
- Any number that is not measured. No invented uptime percentages, no invented
  player counts, no "hundreds of players".
