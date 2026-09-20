# Channel: Reddit

## Read this first

**I could not access Reddit from this environment.** Every route was blocked
(see `research/00-method-and-limits.md` for the full list of attempts). I have
not read the current rules of a single one of these subreddits.

What follows is therefore split into two clearly labelled parts:

- **Measured**: numbers from third-party subreddit-stats services.
- **Prior knowledge, UNVERIFIED**: what I understand these communities'
  rules and conventions to be. This is from training data, it may be out of
  date, and subreddit rules change without notice.

Everything in the second category must be checked before anything is posted.
The checklist at the bottom takes about ten minutes total. `BLOCKERS.md`
item 1 makes this the gating task for the entire Reddit channel.

I would rather hand over a plan with a ten-minute verification step than a
plan that reads as confident and gets `u/nullsect1r` shadowbanned.

## The subreddits

### r/feedthebeastservers: best fit, lowest risk

- **Measured:** ~15,000 members, +12.6% over the past year.
- **Measured:** its own description is *"a place to advertise and seek
  membership of modded Minecraft servers"* and it explicitly welcomes all
  modded servers, not only FTB packs.

This is the only venue in the plan where advertising is the *purpose* of the
community rather than an exception it tolerates. Rule risk is close to zero,
because posting a server here is doing what the subreddit is for.

Small, so expect single-digit responses per post. But those responses are
from people who came to that subreddit specifically to find a modded server,
which is the highest-intent traffic available anywhere on Reddit.

**Start here.** It is the safest possible place to test whether the pitch
works before risking a larger subreddit.

### r/allthemods: highest relevance, needs care

- **Measured:** 123,214 members, created 2014.
- **Note:** `u/nullsect1r` has already posted here. Before writing anything
  new, read back through that account's post history and see what happened:
  what was upvoted, what was removed, what got comments, what got silence.
  That is better evidence than anything I can infer. I could not do this
  because I cannot read Reddit.

**UNVERIFIED expectation:** pack subreddits like this usually permit
server posts under a specific flair, sometimes restricted to a weekly or
monthly thread, and usually with a low-effort-post rule. Some pack subs ban
server advertising entirely and point people at a servers subreddit instead.
**Check which of these is true before posting.**

The realistic best use of this subreddit is not recruitment posts. It is
*content* posts about the pack that happen to be from this server. A good
screenshot of a genuinely interesting build, posted as a build post, reaches
far more of this audience than a recruitment post would, and carries much
less rule risk. The server gets mentioned in the comments when someone asks,
which they do.

### r/feedthebeast: largest, strictest

- **Measured:** 647,835 members.

**UNVERIFIED expectation:** this subreddit has historically prohibited server
advertising outright and redirected it to r/feedthebeastservers. It is
primarily a place for mod discussion, screenshots, technical questions and
pack news.

**Treat it as a no-advertising zone by default.** Assume you cannot post a
recruitment thread here until you have read the rules and confirmed
otherwise. What you *can* do is participate: answer technical questions, post
a genuinely interesting build, write up something you learned. With 648k
members this is the largest pool of the right people anywhere on Reddit, and
the correct way to use it is to be a useful community member whose flair or
comment history mentions a server, not to advertise.

### r/mcservers, r/minecraftserverlist: server-ad subreddits, mostly vanilla

**UNVERIFIED expectation:** these exist specifically for server advertising
and typically enforce a rigid title format with bracketed tags
(`[Java] [SMP] [Modded] [1.21.1]` style), sometimes with a required body
template and a cooldown of a week or a month between posts from the same
server.

My honest assessment: these are overwhelmingly vanilla-server venues, and a
modded server posted there competes with a firehose of SMP ads for a
mismatched audience. Worth one post each to see, not worth a recurring slot
in the calendar. If the first post from each produces nothing, drop them.
This mirrors the server-list finding: vanilla-dominated venues do not convert
for modded servers.

### r/MinecraftBuddies: different shape, possibly useful

**UNVERIFIED expectation:** this subreddit is for finding people to play
*with* rather than advertising servers *at* people, and it usually has a
required post format distinguishing "LFG" from "LFM" (looking for
members/group), often with age and timezone fields.

This shape actually suits this server unusually well, because "we have people
in two hemispheres and you will find someone online" is a statement about
*who you will play with*, which is what that subreddit is for. Worth a
properly formatted attempt.

### Other places worth checking by hand

I could not enumerate subreddits without Reddit access. The owner should
check whether `r/MinecraftServer`, `r/smp` and any ATM-adjacent subs exist
and are active. Do not post to more than the handful named here regardless.
Posting the same thing across many subreddits is the definition of the
behaviour that gets accounts shadowbanned, and it is excluded by the brief.

## Sitewide rules that apply everywhere

**UNVERIFIED but stable for many years, and worth respecting as a floor:**

Reddit's own self-promotion guidance is about ratio and participation, not
about a specific number of posts. The practical version: an account whose
history is nothing but links to the same server is treated as a spam account
by both automated filters and human moderators, regardless of whether any
single post broke a rule.

The protective behaviour is simple and costs nothing: **`u/nullsect1r` should
be a real participant in these communities.** Answer questions about
Mekanism. Comment on other people's builds. Help someone debug a NeoForge
crash. If the account's history is 80% genuine participation and 20% posts
that mention a server, no filter will ever flag it and no moderator will
mind. If it is the reverse, the account is at risk no matter how carefully
each individual post is worded.

This is not a trick to game the ratio. It is the actual reason the rule
exists, and the participation is independently worth doing because it is how
people find out a competent person runs this server.

**Shadowban risk is real and asymmetric.** A shadowban is invisible: posts
appear normal to the poster and are hidden from everyone else, so weeks can
be wasted before it is noticed. Given that, the correct posture is to be
conservative. One post per subreddit, well spaced, is worth more than five
that get the account filtered.

## Cadence

Given the above, the cadence baked into `CALENDAR.md` is deliberately slow:

- No more than one post per subreddit per month, and for most of them, far less.
- Never the same post in two subreddits. Every draft in `assets/reddit/` is a
  genuinely different piece with a different angle, for this reason.
- Comment participation on other people's threads, weekly, with no link
  unless someone asks.

If that feels too slow, the thing to compare it against is the cost of
getting the account banned, which is the loss of the entire channel
permanently.

## The verification checklist

Do this once, before the first post. Roughly ten minutes.

For each of r/feedthebeastservers, r/allthemods, r/feedthebeast,
r/mcservers, r/MinecraftBuddies:

1. Open `reddit.com/r/<name>/about/rules` and read every rule. Not the
   sidebar summary, the full rules page.
2. Note specifically: is server advertising allowed at all? Is it restricted
   to a flair, a megathread, or a particular day? Is there a minimum account
   age or karma requirement? Is there a cooldown between promotional posts?
3. Check whether a pinned megathread for servers exists. If one does, that is
   almost always the correct and safest place to post, and it supersedes
   whatever draft is in `assets/reddit/`.
4. Sort the subreddit by top-of-month and look at what actually succeeded.
   Copy the *form* of what works there, not the form of my drafts.
5. Write what you found into `research/channels-reddit.md` under a new
   "Verified" heading, with the date, and adjust the drafts to match.

Also, specifically for r/allthemods: read `u/nullsect1r`'s own post history
first and record what happened to the earlier posts. That is real data about
this specific account in this specific subreddit, and it beats every
inference in this file.
