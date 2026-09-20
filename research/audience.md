# The audience

## What is actually measurable

I want to be precise about the line between measured and inferred, because
most writing about "the Minecraft audience" is confident and unsourced.

**Measured, 2026-09-20:**

| Figure | Value | How |
|---|---|---|
| ATM10 total downloads | 21.7M | CurseForge project page |
| ATM10 current version | 8.1, released 2026-08-29 | CurseForge files list |
| Official All The Mods Discord | 177,035 members, 59,120 online | Discord invite API, code `allthemods` |
| r/feedthebeast | 647,835 members | reddapi.dev |
| r/allthemods | 123,214 members (created 2014) | reddapi.dev |
| r/feedthebeastservers | ~15,000 members, +12.6% in a year | gummysearch |
| Minecraft LFG (Discord) | 79,404 members, 6,657 online | Discord invite API, code `VVWspYKHTN` |
| Publicly listed ATM10 servers | 43, of which 11 offline | moddedminecraftservers.com |
| Total concurrency across those 43 | ~600, of which ~490 on two servers | same |

The 59,120-people-online figure on the official ATM Discord is the number that
should reframe the whole plan. There is roughly **two orders of magnitude more
attention concentrated in that one Discord than in the entire public ATM10
server-listing ecosystem combined.**

**Not measurable, and I will not invent it:**

There is no public data on ATM10 player age, session length, or churn. I
searched for it specifically and found only generic "average gaming session
by age group" SEO pages that are not about this game, let alone this pack.
Anyone who quotes you a demographic breakdown for ATM10 players is making it
up. See `QUESTIONS.md` Q2 for the one cheap way to get real data here: ask
the existing 32 players.

## What can be inferred defensibly

These are inferences from the structure of the product, not from survey data.
I have flagged my confidence in each.

**ATM10 filters hard for patient, technically-minded players. (High confidence.)**

The reasoning is mechanical, not demographic. To play ATM10 at all you must:
install a third-party launcher (CurseForge, Prism, FTB App), allocate 8-12GB
of RAM to Java, wait through a multi-gigabyte download, and tolerate a
five-minute cold start. Then you are handed roughly 500 mods and a quest book
and told to work it out. The pack's own tagline is "tons of quests and a
proper endgame."

Nobody does that by accident. The install process alone removes casual and
young players far more effectively than any age rule on a server would. This
is why an ATM10 server's audience skews older and more technical than a
vanilla server's, and it is a structural fact about the pack rather than a
guess about who plays it.

**The dominant failure mode is servers dying, not servers being unpleasant. (High confidence.)**

This follows directly from the competitor data, not from vibes. Eleven of 43
listed ATM10 servers were offline at the moment I checked. About thirty
average two players or fewer. Anyone who has looked for an ATM server in the
last year has joined at least one that emptied out.

An ATM10 base is not a weekend project. Getting to a Mekanism fusion reactor
or a full AE2 setup is tens of hours. Players are making a substantial,
non-transferable investment every time they pick a server, and most of the
time it does not pay off. That produces a specific, rational suspicion in
anyone reading a recruitment post, which is worth stating in one sentence
because everything else follows from it:

> The reader's real question is not "is this server nice". It is "will this
> still be here in three months, and is the person running it going to get
> bored".

Almost every competitor's copy answers the first question. Almost none
answers the second. Answering the second, with specifics, is the whole
strategy.

**Performance is a first-class feature to this audience, not a technicality. (High confidence.)**

ATM10 is heavy. A single player exploring generates roughly an order of
magnitude more CPU load than vanilla, and chunk generation is the usual
bottleneck. The community-standard advice is to pre-generate the world with
Chunky before players arrive. Players in this pack talk about TPS the way
other communities talk about ping, and a server that lags on chunk generation
is one people quietly stop logging into.

This means technical claims are not boring filler for this audience. "Twice
daily restarts with countdown warnings", "the world is pre-generated to X
blocks", "here is the TPS" are the kinds of statements that actually persuade
an ATM10 player, and they are exactly the statements a developer-run server
can make truthfully.

Source for the load characteristics and the Chunky convention: community
optimisation writeups and the ATM-10 issue tracker
(`github.com/AllTheMods/ATM-10/issues/787` on chunk-loading freezes). Treated
as convention rather than hard data.

## "Chill SMP" versus "grindy tech server"

The brief asks which of these this server is. I think the dichotomy is the
wrong axis, and picking either label is a mistake here.

**What the two labels actually signal to a reader:**

*"Chill SMP"* is a claim about social norms: nobody grief s you, nobody rushes
you, you can log off for two weeks. It says nothing about the server's
technical quality, and because roughly every server in the competitor set
claims some version of it ("Chill", "Be Nice - Have Fun", "Community Based"),
it now carries close to zero information. Worse, on an ATM pack it can read as
"we are not serious", which repels the exact player who is planning a
hundred-hour automation build.

*"Grindy tech server"* signals a hardcore progression environment, often with
custom rules, a competitive edge, and an expectation of daily play. That is a
much smaller audience, and it is not what this server is. This server has
people with day jobs in two hemispheres who play irregularly. Claiming
"grindy" would attract people who would then find it empty and leave, which
is a retention failure dressed up as a growth win.

**Which this server actually is:** neither. It is an ATM10 server with relaxed
social norms and *seriously run infrastructure*. Those are independent axes
and the interesting thing is that this server is unusual on the second one
while being ordinary on the first.

**What it should claim:** the infrastructure axis, because it is the one where
the claim is both true and rare. Concretely, lead with the operations, and let
"relaxed" be evident from the rules rather than asserted as an adjective.
Something in the shape of: *a small ATM10 server run properly, by someone who
runs servers for a living.* "Relaxed" is then demonstrated, not claimed, by
things like the absence of playtime requirements.

This resolves the tension in the brief. The server does not have to choose
between chill and serious, because those words are describing different
things. It is socially relaxed and operationally serious, and saying exactly
that is more specific than either label alone.

## Where these people actually are, in priority order

Named, with real numbers, and with my read on how reachable each is.

**1. The official All The Mods Discord (177k members, 59k online).**
`discord.gg/allthemods`. Its own public description reads: *"This server is
about Minecraft and Mods. You can also get support for our Modpacks and find
a server to play on."* The community's own operators say it is a place people
go to find a server. This is the densest concentration of exactly the right
audience that exists anywhere, by a very large margin.

I could not verify what its server-advertising channel is called or what its
rules are, because I cannot join it. This is the single highest-value ten
minutes of the owner's time in the whole plan. See `QUESTIONS.md` Q5.

**2. r/feedthebeastservers (~15k members).** Purpose-built: *"a place to
advertise and seek membership of modded Minecraft servers"*, and it explicitly
welcomes all modded servers, not just FTB. Small, but the fit is exact and
advertising is the point of the subreddit rather than a tolerated exception,
which means close to zero rule risk. Growing (+12.6% year on year).

**3. r/allthemods (123k).** The pack's own subreddit. High relevance,
but this is where the greatest care is needed on self-promotion rules, and
`u/nullsect1r` has already posted here. See `channels-reddit.md`.

**4. r/feedthebeast (648k).** The largest modded audience by far, but broad
and generally strict about server advertising. Best approached with genuinely
useful content rather than recruitment. See `channels-reddit.md`.

**5. moddedminecraftservers.com.** Small traffic, but it is the only directory
where the ATM10 category is real and the competitor set is actually present.
Free listing. Low effort, permanent.

**6. Minecraft LFG Discord (79k members, 6.7k online).** Description: *"All
things Minecraft. Find people to play with and new servers to play in."*
Mostly vanilla, so the fit is much worse than the ATM Discord, but the
audience is in "looking for a server" mode, which is worth something.

**Explicitly not where they are:** the general server-list sites. I tested
this rather than assuming it. See `channels-server-lists.md`, which contains
the evidence that these sites' "Modded" categories are effectively
Cobblemon/Pixelmon categories.
