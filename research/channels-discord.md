# Channel: Discord

Discord is the highest-value channel in this plan, for one measured reason.

## The number that decides the strategy

```
$ curl -s "https://discord.com/api/v10/invites/allthemods?with_counts=true"
  guild:   "All The Mods - Modded Minecraft"  (id 254530689225981953)
  members: 177,035
  online:   59,120
  description: "This server is about Minecraft and Mods. You can also get
                support for our Modpacks and find a server to play on."
```

**59,120 people online, right now, in the official Discord of this exact
modpack.** And the community's own description says one of the things you do
there is *find a server to play on*.

For comparison, the entire public ATM10 server ecosystem, all 43 listed
servers added together, has roughly 600 concurrent players, and ~490 of those
are on two large servers.

Everything else in this plan is a rounding error next to that Discord. If
only one channel gets worked, it is this one.

### What I could not verify

I cannot join a Discord server, so I could not read that guild's channel list
or its rules. I do not know what its server-advertising channel is called, or
whether it has one, or what the posting cooldown is. The public description
strongly implies such a space exists, but implication is not a rule I have
read.

**This is the single highest-value ten minutes of owner time in the entire
plan.** See `QUESTIONS.md` Q5 and `BLOCKERS.md` item 4. Join, find the
channel, read the pinned rules, write them down. Everything about how to use
this channel follows from what those rules say, and I would be guessing to
write the post before they are known. A draft written to the most common
shape of such rules is in `assets/discord/atm-discord-post.md`, clearly
marked as needing adjustment.

One warning worth stating plainly: a large official Discord's
advertising channel is also the place where careless self-promotion gets
people banned fastest, and a ban there would cost the best channel available.
Read the rules, follow the cooldown exactly, and do not post twice because
the first one scrolled away.

## Other Discord venues, measured

| Server | Members | Online | Description |
|---|---|---|---|
| All The Mods (official) | 177,035 | 59,120 | "...find a server to play on" |
| Minecraft LFG | 79,404 | 6,657 | "All things Minecraft. Find people to play with and new servers to play in." |

`Minecraft LFG` (invite code `VVWspYKHTN`) is real and sizeable, and its
audience is in active looking-for-a-server mode. But it is a general Minecraft
community, so the great majority of those 79k are vanilla players who will
never install a 500-mod pack. Worth one well-written post in the appropriate
channel; not worth ongoing effort.

Several other advertising Discords surfaced in searches (`Minecraft LFG ::
Advertise & Find Servers`, `Minecraft Advertisement`, `MC Server Advertising`,
`Modded Minecraft LFG`). I could not resolve their invites to get real member
counts, so I cannot rank them and will not pretend to. The `Modded Minecraft
LFG` one is worth the owner finding, because "modded" plus "LFG" is the right
intersection.

**A caution about advertising Discords generally.** Servers whose entire
purpose is people advertising to each other have a structural problem: almost
everyone present is there to post, not to read. Posting in them is close to
free, so it is worth doing once. Expecting real returns from them is not
realistic, and anything that asks for a recurring bump commitment should be
weighed against that.

## Disboard and directory bumping

Disboard blocked my requests, so the following is from its documented
mechanics rather than from reading the site.

- Listing is free. Bumping via the `/bump` command promotes the listing to
  the top of its tag pages.
- The cooldown is **2 hours**, giving a theoretical maximum of 12 bumps a day.
- **Automated bumping is explicitly prohibited** and risks removal of the
  listing. This also puts it out of scope under the brief's no-automation and
  no-manipulation constraints. Do not use an auto-bump bot.

**My assessment: list on Disboard, do not build a bumping habit around it.**

The reasoning is about the owner's time, which the brief names as the scarce
resource. A 2-hour cooldown is an engine for converting attention into a chore.
Realistically it means a handful of manual bumps a day, competing against
servers where a rota of staff bump it twelve times a day, for an audience of
Discord-server browsers rather than modded Minecraft players. The listing
itself is free and permanent and worth having. The bumping treadmill is a bad
trade for a one-person operation with a day job, and I would rather that hour
a week went into the ATM Discord or into content.

If the owner wants to bump, bump when already at the keyboard and it costs
nothing. Never set a reminder for it.

## The server's own Discord is the real Discord problem

This matters more than any external Discord, because every channel in this
plan funnels here, and right now the funnel leaks.

Measured:

```
$ curl -s "https://discord.com/api/v10/invites/r84QJJgUCt?with_counts=true"
  guild name:  "Homies"
  icon:        null
  description: null
  vanity_url:  null
  members: 49, online: 9
  invite lands in: #general
  features: COMMUNITY, NEWS, SOUNDBOARD
  widget: disabled
```

Five problems, all free to fix:

1. **Named "Homies".** A stranger reads this as a closed friend group. See
   `product-audit.md` Finding 2.
2. **No icon.** Renders as a blank grey circle in every embed and directory
   where the invite is posted. Looks abandoned.
3. **No description.** Directory listings and Discord's own preview have
   nothing to show.
4. **Lands new arrivals in `#general`,** mid-conversation between people who
   know each other, with no statement of what the server is, what version to
   install, or how to join.
5. **Widget disabled,** so no external site or bot can show live presence.
   Enabling it is one toggle and lets any listing show "9 online now", which
   is exactly the social proof a browsing stranger wants.

The good news: `COMMUNITY` and `NEWS` are already enabled, so the Onboarding
flow, Rules Screening and announcement channels are all available for free
and just need configuring. Full recommended structure, roles, onboarding flow
and copy are in `assets/discord/structure.md`.

**The order of operations matters.** Fixing the Discord landing experience
should happen *before* the posting starts, not after. Traffic sent into the
current funnel is traffic mostly wasted, and unlike a post, the fix is
permanent and works on every visitor forever. This is exactly the kind of
compounding asset the brief's secondary objective asks for.
