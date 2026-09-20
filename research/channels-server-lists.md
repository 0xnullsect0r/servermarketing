# Channel: Minecraft server list sites

## The test I ran, and why

The standard advice is "submit your server to all the free server lists". I
wanted to know whether that is true for a *modded* server specifically, so I
tested it rather than repeating it.

Method: fetch the "Modded" category page of each major free list and count how
many times "All the Mods" / "ATM10" appears, versus "Cobblemon" and "Pixelmon".
If a site's modded category is really a Pokemon category, an ATM10 server
listed there is invisible no matter how good the description is.

## The result

| Site | "All the Mods" | "ATM10" | "Cobblemon" | "Pixelmon" |
|---|---|---|---|---|
| minecraftservers.org/type/modded | 0 | 0 | **34** | 2 |
| minecraft.buzz/servers/modded | 0 | 0 | **22** | 4 |
| mcserverlist.net | 0 | 0 | 9 | 2 |
| mc-servers.com/category/modded | 0 | 0 | 3 | 3 |
| minelist.io/gamemodes/modded | 1 | 0 | 2 | 3 |
| topg.org/minecraft-servers/type/Modded | 0 | **4** | 0 | 2 |
| **moddedminecraftservers.com** | **43 ATM10 servers listed** | | | |

The actual top of `minecraftservers.org/type/modded`, in rank order:
Cobblemon.gg (655/1000), CobbleGalaxy (410/1000), Cobblemon Delta (307/1000),
MineFury (107/500), Kooplemon (51/500), Cobblemon AU (11/150).

"Modded" on the general lists means Cobblemon. This is not a close call.

## What this means

**The general free server lists are near-worthless for this server, and
submitting to all of them is a way to feel productive without being
productive.** The traffic those sites send is people browsing for a Pokemon
server or a big network. An ATM10 server with 20 slots will be sorted below
several hundred servers with four-digit vote counts, and the handful of
people who do click are not looking for what this is.

There is a second, harder problem. These sites rank by votes, and votes come
from existing players clicking a link daily, usually in exchange for in-game
rewards. A server with 32 players cannot out-vote a network with 600. The
ranking mechanism structurally excludes small servers, and no amount of
copywriting changes that.

There is also a live technical reason that several of these would fail even
if they were worth doing: many of them get their status via mcsrvstat.us,
which **cannot currently resolve `mc.nullsect0r.dev`** (see `product-audit.md`
Finding 4). A listing that renders "offline" is worse than no listing.

## Recommendation, ranked

**Tier 1, do this week (about 30 minutes total):**

1. **moddedminecraftservers.com** — free listing, and the only directory where
   the ATM10 category is genuinely populated. Being listed alongside 43 peers,
   two-thirds of which are dead, is a context where a live, well-described
   server stands out. This is the one list that is clearly worth the effort.
   Listing copy is in `assets/listings/`.

**Tier 2, do once, then ignore (about 20 minutes):**

2. **topg.org** — the only general list with any ATM10 presence at all (4
   mentions, and it supports an `atm10` tag). Free submission. Do not chase
   votes. Submit it, tag it, forget it.

**Tier 3, explicitly not doing, and why:**

- **minecraftservers.org, minecraft.buzz, mcserverlist.net, mc-servers.com,
  minelist.io** — zero ATM presence, vote-ranked, Cobblemon-dominated. The
  expected return is approximately zero players, and the cost is an hour of
  form-filling plus an ongoing nag to vote. Skip all five.
- **Any paid or "featured" tier anywhere.** Out of scope by constraint, and
  the money would be wasted on the above analysis regardless.
- **planetminecraft.com** — I could not read it (Cloudflare blocked my
  requests), so I am not ranking it confidently. My prior is that it is
  vanilla-and-builds dominated and belongs in tier 3, but this is a guess and
  I have marked it as such in `QUESTIONS.md` Q6. It costs 10 minutes to check
  by hand: search the site for "All the Mods" and see whether anything real
  comes back.

## The honest summary

Server lists are worth roughly one hour of total effort, once, and then
nothing. They are not a growth channel for this server. They are a "make sure
we exist if someone searches" hygiene task. Any plan that puts server lists
near the top is a plan written by someone who did not check what is actually
on them.

The single exception is moddedminecraftservers.com, which is worth doing
properly because it is where the actual ATM10 audience-and-competitor set
lives.
