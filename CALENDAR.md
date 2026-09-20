# 90-day calendar: 21 September to 19 December 2026

Specific enough to follow without further thinking. Times are UTC.

**Total ongoing commitment: roughly 1.5 to 2 hours a week after week 1.**
Week 1 is heavier (about 5 hours) because it is the setup that everything
else depends on.

## Cadence rules baked in

These come from `research/channels-reddit.md`. They are the constraint the
calendar is built around, not suggestions.

- **Never more than one post per subreddit per month.** Most get far less.
- **Never the same post in two places.** Every draft is genuinely different.
- **Comment participation weekly**, no links unless asked.
- If a subreddit's real rules (once verified) specify a longer cooldown,
  **their rule wins over this calendar**, always.

If this feels too slow: the thing to weigh it against is a shadowban, which
would cost the entire Reddit channel invisibly and permanently.

---

# Phase 0: Fix the product (week 1)

**Nothing is posted this week.** This is deliberate. Traffic sent into the
current funnel is largely wasted, and the fixes below are permanent while a
post is not. If only one week of this plan happens, make it this one.

### Mon 21 Sep, ~90 min: the decisions

- [ ] **Decide the ATM10 version question.** Update to 8.1, or commit to
      staying on 7.1 and stating it loudly everywhere. Doing neither is the
      current state and it is the worst option. `BLOCKERS.md` item 2.
- [ ] **Decide the public name.** `assets/core-messaging.md`.
- [ ] **Decide the wipe policy** and whether you will commit to it publicly.
      `[VERIFY-2]`.
- [ ] **Raise the slot cap** in `server.properties` above the size of the
      existing player base. Currently 20 against ~32 players.
- [ ] Set `enable-query=true` while you are in there.

### Tue 22 Sep, ~30 min: Discord quick wins

- [ ] Set a server icon (temporary crop is fine, better one comes Thursday).
- [ ] Set the server description.
- [ ] Enable the server widget.
- [ ] Create `#start-here` and pin the copy from
      `assets/discord/structure.md`.
- [ ] Repoint the invite to land in `#start-here` instead of `#general`.

### Wed 23 Sep, ~45 min: measurement and DNS

- [ ] Start the hourly status cron job. `assets/systems/tracking.md` §1.
      **Do this today**, because the seven-day timezone measurement gates
      several public claims and the clock starts now.
- [ ] Investigate the mcsrvstat DNS failure. `BLOCKERS.md` item 3.
- [ ] Create the labelled Discord invite links.
      `assets/systems/tracking.md` §3.

### Thu 24 Sep, ~2 hours: the screenshots

- [ ] Take the spawn screenshot set. `assets/content/ideas.md`, idea 1.
      Six shots, HUD off, render distance 16+, dawn or dusk.
- [ ] Make the 64x64 server icon from the tower shot. Set it on both the
      Minecraft server and the Discord.

### Fri 25 Sep, ~15 min: the cheapest growth in the plan

- [ ] Post the forwardable one-liner from `assets/core-messaging.md` in the
      Discord, asking existing players to invite someone. Segment D converts
      better than anything else here and costs nothing.

### Weekend 26-27 Sep

- [ ] Nothing scheduled. Rest, or do the elytra clip if you feel like it.

---

# Phase 1: Verify and test (weeks 2-3)

## Week 2: 28 Sep - 4 Oct

### Mon 28 Sep, ~20 min
- [ ] **Join `discord.gg/allthemods`.** Find the server-advertising channel.
      Read its pinned rules completely. Read twenty recent posts. Write what
      you find into `research/channels-discord.md` under a "Verified"
      heading with today's date.
      **This is the highest-value 20 minutes in the entire plan.**

### Tue 29 Sep, ~20 min
- [ ] **Run the Reddit verification checklist.**
      `research/channels-reddit.md`, bottom section. All five subreddits.
- [ ] Read `u/nullsect1r`'s own post history in r/allthemods and record what
      happened to the earlier posts.

### Wed 30 Sep, ~30 min
- [ ] **Read the seven days of status data.** `assets/systems/tracking.md`
      §1. Resolve `[VERIFY-1]`.
- [ ] Update every draft in `assets/` to use the strong or fallback wording
      accordingly. Do this now while it is one pass over the files.

### Thu 1 Oct, ~30 min
- [ ] **Post to r/feedthebeastservers.**
      `assets/reddit/01-ftbservers-recruitment.md`. Target 14:00-16:00 UTC.
      This is the safest venue and it is a cheap test of the pitch.
- [ ] Check back every few hours. Reply to every comment.

### Fri 2 Oct - Sun 4 Oct
- [ ] Reply to anything on the post, same day.
- [ ] 3-4 useful comments on other people's threads in r/feedthebeast or
      r/allthemods. No links. `assets/reddit/comment-engagement.md`.

## Week 3: 5 - 11 Oct

### Mon 5 Oct, ~15 min
- [ ] Record the week's three numbers in `LOG.md`.
- [ ] Write the post-mortem for the r/feedthebeastservers post, good or bad.

### Tue 6 Oct, ~40 min
- [ ] **Post in the official ATM Discord**, following the rules you recorded
      in week 2. `assets/discord/atm-discord-post.md`. Attach the hero
      screenshot if images are allowed.
- [ ] Watch for replies for the rest of the day.

### Wed 7 Oct, ~30 min
- [ ] **Submit to moddedminecraftservers.com.** `assets/listings/`.
- [ ] Verify an hour later that the listing shows **online**. If it shows
      offline, switch the address to `23.161.184.9`.

### Thu 8 Oct, ~20 min
- [ ] Create the Disboard listing. `assets/discord/directory-listings.md`.
      Then forget about it. No bump reminders.
- [ ] Submit to Discadia.

### Fri 9 Oct - Sun 11 Oct
- [ ] Weekly comment participation, 15 min.
- [ ] Answer a few support questions in the ATM Discord. Not a pitch, just
      being useful.

---

# Phase 2: Steady cadence (weeks 4-13)

From here the pattern repeats monthly. The weekly baseline is small on
purpose, because a plan that survives a bad week is worth more than an
ambitious one that gets abandoned.

## The weekly baseline, every week

- **Mon, 5 min:** record the three numbers in `LOG.md`.
- **Any day, 15 min:** 3-4 useful comments on other people's threads. No
  links. This is what protects the whole Reddit channel and it is the most
  commonly skipped item here, so do it early in the week.
- **Ongoing:** welcome every new Discord member by name, same day. Answer
  every question in `#help-and-questions` within 24 hours. An unanswered
  question is the most expensive thing that can happen in that Discord.

## Week 4: 12 - 18 Oct

- [ ] **Thu 15 Oct:** post the elytra course clip to the Discord and
      YouTube. `assets/content/ideas.md`, idea 2.
- [ ] **Sat 17 Oct:** post to r/MinecraftBuddies, 16:00-19:00 UTC.
      `assets/reddit/04-minecraftbuddies-lfg.md`. Follow their required
      format exactly.

## Week 5: 19 - 25 Oct

- [ ] **Tue 20 Oct:** build the status page. 3 hours.
      `assets/website-spec.md`. Start using it as the canonical link
      everywhere.
- [ ] Baseline only otherwise.

## Week 6: 26 Oct - 1 Nov

- [ ] **Sun 1 Nov:** post the spawn build to r/allthemods, 15:00-18:00 UTC.
      `assets/reddit/02-allthemods-build.md`. **No link in the body.**
      Answer in the comments when someone asks.
- [ ] Clear your evening. This is the highest-reach post in the plan and the
      comments matter more than the post.

## Week 7: 2 - 8 Nov

- [ ] **Mon 2 Nov, 30 min: the monthly review.**
      `assets/systems/tracking.md` §5. Check the 14-day retention number.
      **If retention is below a third, stop posting and fix the server
      experience instead.**
- [ ] **Wed 4 Nov:** post the monthly state-of-the-server to
      `#announcements`. `assets/templates/templates.md`.

## Week 8: 9 - 15 Nov

- [ ] **Wed 11 Nov:** post to r/feedthebeast, 15:00-17:00 UTC.
      `assets/reddit/05-feedthebeast-discussion.md`. **No link, no server
      mention, at all.** The answers are free market research on what the
      core segment evaluates.
- [ ] Read every reply properly. Update `assets/core-messaging.md` based on
      what people actually say they look for.

## Week 9: 16 - 22 Nov

- [ ] **Sat 21 Nov:** post to r/mcservers, 17:00-20:00 UTC.
      `assets/reddit/06-mcservers-listing.md`. Follow their title format
      exactly. Low expectations; this is an experiment.
- [ ] **Tue 17 Nov:** submit to topg.org with the `atm10` tag. 20 min. Then
      ignore it.

## Week 10: 23 - 29 Nov

- [ ] **Quiet week by design.** Baseline only.
- [ ] Optional, if the mood takes you: gather the real numbers for the
      r/admincraft writeup (TPS, pregen radius, RAM, what broke).

## Week 11: 30 Nov - 6 Dec

- [ ] **Tue 1 Dec:** post the technical writeup to r/admincraft,
      13:00-15:00 UTC. `assets/reddit/03-admincraft-technical.md`.
      **Only if you have real measured numbers.** Skip it otherwise; a post
      with invented figures in front of 150k admins is worse than no post.
- [ ] **Wed 2 Dec:** monthly state-of-the-server post.

## Week 12: 7 - 13 Dec

- [ ] **Second r/feedthebeastservers post**, if their cooldown allows (check
      what you recorded in week 2). Rewrite it based on everything learned
      since October rather than reposting the original.
- [ ] Optional: start the open-source automation repo.
      `assets/content/ideas.md`, idea 8.

## Week 13: 14 - 19 Dec

- [ ] **Mon 14 Dec, 45 min: the 90-day review.** Compare against the honest
      expectation in `STRATEGY.md` §4: 10-25 people trying the server, 3-8
      becoming regulars.
- [ ] Decide what to keep and, more importantly, **what to delete.** Any
      channel that produced nothing in 90 days should come out of the
      calendar rather than being carried forward out of optimism.
- [ ] Write the quarterly public state-of-the-server post. This is the first
      entry in what becomes the durability track record.

---

## Notes on the shape of this calendar

**Week 1 has no posting in it.** That is the most important design decision
here. Everything else is downstream of the version question and the Discord
landing experience.

**Only six Reddit posts in 90 days, across five subreddits.** This will feel
too slow. It is calibrated against the cost of losing the account, which is
the whole channel, invisibly.

**Weeks 10 and parts of 5 are deliberately empty.** A calendar with something
in every slot is a calendar that gets abandoned in week four. The empty weeks
are load-bearing.

**If a week gets missed, skip it rather than catching up.** Doubling up posts
is exactly the pattern that looks like spam to both filters and moderators.
The baseline participation matters more than any individual post, so if you
only do one thing in a busy week, make it the 15 minutes of comments.
