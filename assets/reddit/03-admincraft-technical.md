# Post 3: r/admincraft, technical writeup

**Target:** r/admincraft (150,270 members, founded 2012)
**Angle:** A genuinely useful operational writeup. No recruitment whatsoever.

Self-described as *"a subreddit for Minecraft administrators and developers
who are serious about cultivating a quality server with a quality
community."* The audience is admins, not players shopping for a server, so
treat this as a credibility and community-membership play rather than a
growth one.

## Why post this at all, honestly

It will not fill the server. Almost nobody here is looking for somewhere to
play. What it does:

1. Makes `u/nullsect1r` an account with a history of being useful rather than
   an account that only posts server ads. That is what protects the entire
   Reddit channel from being read as spam (`research/channels-reddit.md`).
2. Reaches Segment C, the technically curious player, who is small but
   retains extremely well.
3. Produces an artefact that keeps being found through search for years.

If that framing does not appeal, skip this post. It is genuinely optional.
What is not optional is that the account participates *somewhere*.

## Rules to check

At `reddit.com/r/admincraft/about/rules`:
- [ ] Self-promotion rules. This post contains none, but check anyway.
- [ ] Is there a flair for guides or discussion?
- [ ] Any rule against mentioning your own server even in passing? If so,
      strip the one reference and post it anyway. It loses nothing.

## Timing

Tuesday to Thursday, 13:00-15:00 UTC. Weekday, working hours, because this is
a professional-interest audience.

## What a good outcome looks like

30-80 upvotes and a real technical discussion in the comments. Somebody
correcting you is a good outcome, not a bad one. Zero new players is the
expected outcome and is fine.

## Prerequisite

**You have to have the real numbers.** Do not write this post with invented
figures. If you do not have TPS measurements, pregeneration settings and RAM
allocation to hand, gather them first, or write about something you did
measure. A technical post with made-up numbers in front of 150k admins is the
worst possible outcome for the account's credibility.

---

## Title

```
What it actually took to get All the Mods 10 stable with 20 players on one box
```

Alternatives:

```
ATM10 server tuning: the numbers that mattered and the ones that didn't
```

```
Running ATM10 (500 mods, 1.21.1 NeoForge) on a dedicated box: pregen, restarts, and what broke
```

## Body

```
I run a small All the Mods 10 server, 1.21.1 on NeoForge, on a dedicated box.
This is a writeup of what actually moved the needle on stability, because
most of what I found when I was searching was either generic "reduce your
view distance" advice or hosting company blog posts.

Numbers first, so you know whether this is relevant to you:

- Hardware: [CPU, RAM, disk. Be specific. "Dedicated box" means nothing on
  its own.]
- Allocated heap: [XX]GB
- Players: typically [X] concurrent, [XX] registered
- TPS at that load: [measured, not estimated]
- Pack: All the Mods 10 [version], roughly 500 mods

What made the biggest difference:

1. Pregeneration. [How far, what tool, how long it took, what it fixed.
   Chunky is the community-standard answer. Say what radius and why.]

2. Scheduled restarts. Twice a day, with countdown warnings in chat. [Say
   what the warnings are, how they are triggered, what the schedule is, and
   what specifically got better after introducing them. Memory creep is the
   usual honest answer.]

3. [Third thing that actually helped.]

What did not make a difference, despite being widely recommended:

- [Be specific here. This is the most valuable section of the post and the
  one that will get the comments, because everyone has been told to do
  things that did not work and nobody writes that part down.]

What is still not solved:

- [Whatever is still annoying. Admitting this is what makes the rest
  credible, and this subreddit will have answers.]

Tooling: I use Crafty Controller for management and [backup tool] for
backups, which I have actually restored from rather than merely configured.

Happy to go into detail on any of it.
```

## Notes

The "what did not work" section is the most valuable part and the reason to
write the post at all. Everyone publishes what worked. Almost nobody
publishes what they tried that did not, and it is the thing admins most want
to read.

Mention the server by name at most once, in passing, and only if the rules
allow it. The post works fine without it.
