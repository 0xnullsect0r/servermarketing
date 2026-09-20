# Channels: short-form video, modpack platforms, and the one nobody is using

## Short-form video (TikTok, YouTube Shorts, Reels)

### What the advice says, and why I discount most of it

Search results on this topic are almost entirely hosting companies and
short-form marketing agencies. The recurring claim is the lottery framing:
tickets are free, most videos do nothing, one hit brings more players than a
year of server lists, so post several a week for months.

The framing is not wrong. But notice who benefits from you believing it: the
people selling the hosting you need for the players, and the agencies selling
the editing. "Post several videos a week for months" is a very large ask
dressed up as a small one, and the brief is explicit that the owner is one
person with a day job and other projects.

### My honest assessment

**A sustained short-form content habit is not a good fit here, and I do not
recommend committing to one.** The reasons are specific:

1. **The cost is recurring and the payoff is a lottery.** Three videos a week
   for three months is roughly forty pieces of work. If the owner misses two
   weeks, the algorithm treats the account as cold and much of the accrued
   benefit is gone. That is the opposite of the brief's secondary objective,
   which asks for assets that keep working without ongoing effort.
2. **The audience match is poor at the top of the funnel.** TikTok's Minecraft
   audience skews heavily toward young, vanilla, mobile players. ATM10 filters
   for people who will allocate 10GB of RAM to a Java process. A viral Minecraft
   short mostly reaches people who will never install this pack. High views
   would not mean high joins, and the brief asks to optimise for fit over volume.
3. **Retention-weighted growth argues against it.** Even in the success case,
   short-form delivers impulse joiners, which is precisely the cohort that
   joins once and leaves.

### What I do recommend instead

**Make a small number of permanent artefacts, not a content habit.**

The custom spawn is a genuine asset and it is currently unphotographed. A
handful of good screenshots and one flyover video are worth making *once*,
because unlike a TikTok they never expire: they go in the Reddit posts, the
directory listing, the Discord, the website, and every future post for the
next year. That is the compounding version of content.

If a clip happens to be worth posting to YouTube as an unlisted-then-public
flyover so it can be embedded, fine, that is free. But the goal is the
artefact, not the channel. Concrete plan in `assets/content/ideas.md`.

One exception worth naming: if the owner or a player *enjoys* making videos,
all of the above is wrong, because the cost calculus changes completely when
the work is not a chore. I am arguing against committing to it as a
marketing obligation, not against anyone doing it for fun.

### Creator outreach

The advice to approach small creators (a few hundred to a few thousand
followers) is sound in principle and it is free. But it runs directly into a
hard constraint in the brief: **no contacting individuals who have not opted
into being contacted.** Cold-DMing creators is out.

The version that stays inside the constraint: if a creator turns up and
plays, make it easy and interesting for them, and say yes if they ask for
anything reasonable. That is reactive, not outbound, and it costs nothing.
Do not build a plan around it.

## CurseForge and Modrinth

I checked both for server-listing or community surfaces.

**CurseForge:** the ATM10 project page (21.7M downloads) has no comments
section and no server directory. It links to the pack's GitHub and its
Discord. There is no surface here to post a server on.

**Modrinth:** has a "Servers" section, but this is a *hosting product*
(Modrinth selling server hosting), not a community directory where you can
list your own box. Not a channel.

**Conclusion: neither platform is a promotion channel.** Their value is
indirect and worth understanding: CurseForge is where players get the pack,
which is why the version mismatch in `product-audit.md` Finding 1 matters so
much. The install page is the top of the funnel and it currently hands people
8.1 while the server runs 7.1.

## r/admincraft and the technical-credibility angle

- **Measured:** 150,270 members, founded 2012. Self-described as "a subreddit
  for Minecraft administrators and developers who are serious about
  cultivating a quality server with a quality community."

This is a strong fit for the *owner*, not for the server. The people there are
admins, not players looking for somewhere to play, so a recruitment post would
be off-topic and unwelcome. But a genuinely useful technical writeup about
running ATM10 at scale is exactly what that subreddit is for, and it is
something this owner can write truthfully and few others can.

The honest caveat: this converts to players slowly and indirectly, if at all.
Admins are also players sometimes, and credibility produces links and goodwill,
but nobody should expect a technical post to r/admincraft to fill the server.
Its value is that it makes `u/nullsect1r` a known competent person rather than
an account that only posts server ads, which is what protects the whole Reddit
channel (see `channels-reddit.md`).

## The channel nobody in this space is using well

This is the thing the brief asked me to look hardest for, so I want to make
the case properly rather than just assert it.

**Observation:** across all 43 ATM10 servers, the competition is competing on
*description*. Everybody writes adjectives into a listing. Nobody is
competing on *artefacts*. There is essentially no ATM10 server that has
published anything a person would find useful on its own terms.

**The owner's unfair advantage:** he is a professional software developer who
already operates this server on Crafty Controller with scheduled restarts and
real backups. The work of running it well is already done. It is simply not
written down anywhere.

**The play: publish the operational work as free, open artefacts, with the
server as the reference deployment.**

Concretely, any of:

- A public status page for the server (live player count, version, uptime,
  next restart), served from the box that already exists. This doubles as the
  single link that fixes the "is anyone on" question everywhere.
- The restart-warning and backup automation, cleaned up and put on GitHub with
  a readme, for other ATM10 operators to use.
- A written, numbers-included post on what it actually takes to keep ATM10 at
  a good TPS: pregeneration settings, RAM allocation, what broke, what fixed it.

**Why this is genuinely underused rather than just unusual:**

1. It is the only form of promotion on this list that *cannot* be copied by the
   other 42 servers, because almost none of them are run by someone who could
   write it.
2. It is permanent. A GitHub repo or a technical post keeps being found through
   search for years. A Disboard bump lasts two hours.
3. It inverts the credibility problem. The audience's real question is "will
   this server still be here in three months and is the owner competent". A
   public artefact demonstrating competence answers that question in a way no
   amount of copy can, because it is evidence rather than assertion.
4. It is work the owner is good at and will plausibly enjoy, which matters
   enormously for something that has to survive contact with a day job.

**The honest limits of this idea,** because I do not want to oversell it:

- It is slow. This is a six-month play, not a thirty-day one.
- It reaches admins and technical players, not the general ATM10 audience. It
  will never be the main source of players.
- It only works if the artefacts are genuinely useful. A thin repo published
  as a marketing move is worse than nothing, and this audience can tell.

So: this is the best *secondary* channel and the best long-term investment,
and it is not a substitute for the Discord and Reddit work. I would put it at
a few hours a month, not more. It is ranked accordingly in `STRATEGY.md`.
