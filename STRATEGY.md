# Strategy

Written 2026-09-20, after the research in `research/`. Every claim here traces
back to something measured in those files. Where I am uncertain I say so.

---

## The one-paragraph version, before anything else

The biggest growth problem this server has is not distribution. It is that the
server runs ATM10 7.1 while everyone who installs the pack today gets 8.1, and
that every public surface is branded as somebody else's friend group. Those two
things silently cancel most of the value of any posting anyone does. Fix them
first. After that, the plan is narrow on purpose: one Discord, two subreddits,
one directory, and a small number of permanent artefacts built around the
custom spawn. Everything else on the usual list is deliberately not being done,
and section 4 argues why.

---

## 1. Positioning statement

> **Homies' International is a 20-to-30-person All the Mods 10 server run by a
> working software engineer on a dedicated box in a Pennsylvania datacenter.
> Its player base is split between the US and New Zealand, so there are people
> online at hours when a single-region server is empty. It restarts twice a
> day on a schedule with countdown warnings, it takes real backups, and the
> person who runs it will fix your problem, because it is his server and he
> does this for a living. There is no store, no ranks for sale, and nothing
> to buy. It is for adults who want their base to still be there in six
> months.**

That paragraph is written to fail the generic test: it would be false if
applied to almost any other server in the competitor set. The datacenter, the
two-hemisphere player base, the twice-daily scheduled restarts and the
occupation of the owner are all specific and all checkable.

**What it deliberately does not say.** It does not say "friendly", "chill",
"welcoming" or "great community". Those words appear in most of the 43
competitor listings and therefore carry no information (`competitors.md`,
section "What the shape of this data actually says", point 3). It does not
say "no pay to win" in the headline either, for the same reason: on ATM
servers that is the default, not a feature. Both appear lower down as
specifications, where a reader ticking boxes will find them.

**Two load-bearing caveats.**

1. **"International" is not yet verified.** I can confirm the timezone
   arithmetic and that the owner says there are New Zealand players. I cannot
   confirm anyone is actually online at 09:00 UTC. This claim must be measured
   for one week before it goes in public copy (`product-audit.md` Finding 5;
   method in `assets/systems/tracking.md`). If the data does not support it,
   the honest fallback is in `assets/core-messaging.md`.
2. **"Homies' International" is a naming suggestion, not a decision.** The
   problem with "Homies" alone is set out in `product-audit.md` Finding 2. The
   options, including keeping the name, are argued in
   `assets/core-messaging.md`. This is the owner's call and the rest of the
   plan works with any of them.

---

## 2. Audience segments

Four segments, ranked by how much they are worth per person acquired.

### Segment A: The returning ATM player whose last server died
**The core target. Most of the effort should aim here.**

Who: has played ATM9 or ATM10 before, probably on a public server that emptied
out or wiped. Knows what AE2 and Mekanism are. Wants to start a base and have
it still exist in March. Has been burned and is now suspicious.

Why they are the best segment: highest retention by a wide margin, because
they already know the pack, they are not going to bounce off the install, and
they are explicitly shopping for durability, which is this server's genuine
strength. Evidence that this segment is large: 11 of 43 listed ATM10 servers
were offline when I checked and ~30 average two players or fewer
(`competitors.md`). Every one of those dead servers produced players who are
now looking.

What convinces them: operational specifics. Restart schedule, backup policy,
a public position on wipes, who runs it and whether he is going anywhere.
Not adjectives.

Reached by: the official ATM Discord (primary), r/feedthebeastservers,
r/allthemods, moddedminecraftservers.com.

### Segment B: The adult with a job and irregular hours
Who: 25-40, plays a few evenings a week, cannot commit to a schedule, does not
want to be the only person online, does not want drama.

Why they matter: they are the most retention-stable players there are, they
are the ones who stay for a year, and the two-hemisphere coverage is aimed
squarely at them. "There is usually someone on" is worth more to this person
than any feature. Note the competitor "ATM10 for Grownies" exists, which is
evidence the segment is recognised, and it is at 0/20, which is evidence
nobody has served it well.

What convinces them: no playtime requirements, no obligation, someone online
at odd hours, a grown-up moderation posture.

Reached by: the same channels as A, plus r/MinecraftBuddies, which is
structurally about who you will be playing with.

### Segment C: The technically curious player who cares about how it is run
Who: reads about TPS, has run a server themselves, notices when chunk
generation stutters, appreciates that someone pregenerated the world.

Why they matter: small segment, but they are disproportionately the people who
become regulars and help other players, and they are the only segment that can
be reached through the owner's own professional competence. Also the segment
most likely to forgive a rough edge if the reasoning is explained.

What convinces them: the artefacts. A status page, a public writeup of the
server's tuning, the automation on GitHub.

Reached by: r/admincraft (150k), r/feedthebeast technical threads, the
open-source artefacts in `assets/content/ideas.md`.

### Segment D: The existing friend group and their friends
Who: the ~49 people already in the Discord and whoever they would bring.

Why they are listed last but are not least: this is the cheapest and
highest-converting growth available and it requires no marketing at all. A
personal invitation from an existing player converts at a rate no Reddit post
will ever approach, and those players arrive already socially anchored, which
is the strongest retention predictor there is.

What convinces them: being asked, once, with something easy to forward.

Reached by: the owner asking in the Discord, and a forwardable one-liner
(`assets/core-messaging.md`). This is in the week-one plan for a reason.

---

## 3. Channel priority

Ranked by expected retained players per hour of owner time.

| Rank | Channel | Effort | Why |
|---|---|---|---|
| 0 | **Fix the product surfaces** | ~3 hours, once | Not a channel, but it multiplies every channel below. See §5. |
| 1 | **Official ATM Discord** (177k / 59k online) | 30 min to learn the rules, then occasional | Two orders of magnitude more of the right people than everything else combined, and its own description says people go there to find a server. |
| 2 | **The server's own Discord** | ~3 hours, once | Every other channel funnels here and it currently leaks. Permanent, compounding. |
| 3 | **r/feedthebeastservers** (15k) | 30 min per post, monthly at most | Purpose-built for exactly this. Near-zero rule risk. Small but perfect intent. |
| 4 | **Existing players' invitations** | 15 minutes | Highest conversion and retention of anything on this list. |
| 5 | **r/allthemods** (123k) | 1-2 hours per post, rare | High relevance, but content posts not recruitment posts, and rules must be read first. |
| 6 | **moddedminecraftservers.com** | 30 min, once | The only directory where the ATM10 category is real. |
| 7 | **Permanent artefacts** (spawn screenshots, status page, writeups) | A few hours a month | Slow, compounding, and uncopyable by competitors. |
| 8 | **r/feedthebeast** (648k) | Ongoing participation | Not for advertising. For being a known useful person, which protects the whole Reddit channel. |
| 9 | **r/MinecraftBuddies, r/admincraft, Minecraft LFG Discord, topg.org** | One attempt each | Cheap, plausible, unproven. Try once, drop if nothing. |

### What I am explicitly not doing, and why

Saying no is the part of this that saves the most time.

**Not doing: the general server lists** (minecraftservers.org, minecraft.buzz,
mcserverlist.net, mc-servers.com, minelist.io). I tested these rather than
assuming. Their "Modded" categories contain 0-1 mentions of All the Mods
against 2-34 mentions of Cobblemon (`channels-server-lists.md`). They rank by
vote volume, which structurally excludes a 20-slot server competing against
networks with 600 players. Expected return: approximately zero. Cost: an hour
of forms plus a permanent low-grade obligation to nag players to vote. Skip.

**Not doing: a Disboard bumping habit.** The listing is free and worth having.
The 2-hour bump cooldown is an engine for converting a one-person operation's
scarce attention into a chore, competing against servers with staff rotas
bumping twelve times a day, for an audience of Discord browsers rather than
ATM players. Auto-bumping is prohibited by Disboard and excluded by the brief
anyway. List it, never set a reminder for it.

**Not doing: a sustained short-form video habit.** Argued at length in
`channels-content.md`. Briefly: the cost is recurring and large (roughly forty
pieces of work over three months), the payoff is a lottery, TikTok's Minecraft
audience is overwhelmingly young and vanilla while ATM10 filters for people who
will allocate 10GB of RAM to Java, and even the success case delivers impulse
joiners, which is the cohort the brief explicitly says not to optimise for.
Making a small number of permanent artefacts from the spawn is a much better
use of the same hours. If the owner enjoys making videos this reasoning does
not apply, because the cost calculus changes when the work is not a chore.

**Not doing: creator outreach.** Cold-contacting small creators is the standard
advice and it is excluded by the brief's constraint against contacting people
who have not opted in. The reactive version, being good to any creator who
shows up on their own, is free and is in the plan.

**Not doing: posting to many subreddits.** Six or seven named subreddits is
the whole list, and most get one post. Shotgunning is what gets accounts
shadowbanned, and a shadowban would cost the entire Reddit channel invisibly.

**Not doing: CurseForge or Modrinth as promotion channels.** Checked; neither
has a surface for it. CurseForge has no comments and no directory, and
Modrinth's "Servers" is a hosting product.

---

## 4. The honest assessment

The brief asks me to say plainly what is hard, slow, or unlikely to work. This
section is the most useful one in the document and I have not softened it.

**The version gap is the whole ballgame, and no amount of good copy routes
around it.** The server is on 7.1. A person who reads a great post, installs
ATM10 and clicks connect gets 8.1 and bounces. They will not file a bug report
about it; they will assume the listing is stale. Until this is resolved, every
hour spent on promotion is partially wasted, and I would rather say that than
hand over a calendar that quietly burns the owner's time. There is a real
argument for not updating a live world mid-flight, and it deserves respect. But
"do not update" and "recruit publicly" are incompatible unless the version is
stated loudly and early everywhere, which is the third option in `BLOCKERS.md`
item 2. Doing neither is the current state and it is the worst of the three.

**Realistic numbers, so nobody is disappointed by success.** If everything in
this plan is executed well, I would expect something like 10-25 new people
trying the server over 90 days, of whom perhaps 3-8 become regulars. That
would be a genuinely good outcome: it would roughly double the active core and
put this server third or fourth in the entire public ATM10 category by average
concurrency (`competitors.md`). It is also a long way from "a full server". If
the goal is 100 concurrent players, this plan will not get there and no free
plan will; that is a different product requiring a network, a store to fund
it, and staff.

**Reddit is the biggest known unknown in this document.** I could not read a
single subreddit rule (`00-method-and-limits.md`). The drafts are conservative
and each ships with a verification checklist, but I want to be clear that I am
handing over inference where I would prefer to hand over fact. Ten minutes of
the owner's time converts that inference into fact, and until it is done the
Reddit portion of the calendar should be treated as provisional.

**The single best channel is the one I could verify least.** The official ATM
Discord is, by measurement, worth more than everything else on the list
combined. I could not join it, so I do not know what its advertising channel
is called or what its cooldown is. This is frustrating and it is also the
easiest thing on the list to resolve.

**Growth will be lumpy and mostly invisible.** Most posts will do nothing. This
is normal and is not evidence the plan is wrong. The failure mode to guard
against is not "a post flopped"; it is concluding after three quiet weeks that
none of it works and stopping, two weeks before the thing that would have
worked. The tracking in `assets/systems/tracking.md` exists mainly so that
judgement is made on data rather than on mood.

**The largest risk is not a marketing risk.** It is that a successful campaign
brings in people faster than a 20-slot server and a friend-group Discord can
absorb them, and they have a mediocre first experience and leave, and the
server is worse off than before because now it has a reputation. This is why
section 5 is ordered the way it is, and why I would genuinely rather the owner
did only section 5 and no posting at all than the reverse.

**What would change my mind about the ranking.** If the version gap is closed
and the ATM Discord turns out to prohibit server advertising entirely, then
r/feedthebeastservers and the artefact strategy become the whole plan, and
expectations should drop accordingly. If the one-week timezone measurement
shows genuine Pacific-hours coverage, the "International" angle gets stronger
and should be pushed harder than I have pushed it here.

---

## 5. Order of operations

The ordering is the strategy. Do not reorder it.

**Phase 0, this week, before any posting.** Resolve the version question. Set
the Discord icon and description, and add a landing channel so arrivals do not
drop into `#general`. Raise the slot cap above the size of the existing player
base. Take the spawn screenshots. Ask the existing players to invite someone.

**Phase 1, weeks 2-3.** Join the ATM Discord and read its rules. Verify the
subreddit rules. Run the one-week timezone measurement. Post once to
r/feedthebeastservers, which is the safest venue, and use it to test whether
the pitch lands before risking a bigger one.

**Phase 2, weeks 4-12.** The calendar in `CALENDAR.md`, at the deliberately
slow cadence set in `channels-reddit.md`.

Phase 0 is roughly three hours and is worth more than Phases 1 and 2 combined.
If the owner does nothing else, do Phase 0.
