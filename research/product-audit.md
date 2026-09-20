# Product audit: what a stranger actually encounters

This is the most important file in `research/`. Four of the findings below are
worth more than any amount of posting, because they each silently cancel out
marketing effort that has already been spent.

Everything here was measured on 2026-09-20 and is reproducible.

---

## Finding 1 (critical): the server runs ATM10 7.1, the world has moved to 8.1

Measured:

```
$ curl -s https://api.mcstatus.io/v2/status/java/mc.nullsect0r.dev
  "version": {"name_clean": "1.21.1", "protocol": 767}
  "motd":    "Homies' International Server / All The Mods 10 v7.1"
```

ATM10's release history on CurseForge:

| Pack version | Released |
|---|---|
| 7.1 | 2026-06-26 <- **the server** |
| 7.2 | 2026-07-20 |
| 7.3 | 2026-08-02 |
| 8.0 | 2026-08-14 |
| 8.1 | 2026-08-29 <- **what a new player installs today** |

The server is four releases and just under three months behind current.

Why this outranks everything else: a person who reads a recruitment post,
opens CurseForge or the FTB/Prism launcher, clicks install on All the Mods 10
and hits connect will get **8.1**, and will not be able to join. To play here
they have to know to install a specific older version, find 7.1 in the version
dropdown, and install it as a separate instance. Some fraction of people will
do that. Most will assume the server is dead or the listing is stale, and
leave without ever saying anything.

Every post, listing and Discord invite drives traffic into that wall. Fixing
the wall is worth more than doubling the traffic.

8.1 is also not a quiet patch. It added Ad Astra, a full space-exploration mod
with rockets, oxygen and space suits. That is the kind of thing players
actively search for and ask about. "We're on 7.1" reads, to an ATM player who
follows the pack, as "we have not been updated since June."

There is a real argument on the other side and it should be taken seriously:
updating a pack mid-world on a server with existing bases can break things,
and an owner who has 32 people with established builds is right to be
cautious. That is a legitimate reason to delay. It is not a reason to
recruit publicly while delayed. See `BLOCKERS.md` item 2 for the fork in
the road: either update, or say the version clearly and early in every
public asset so nobody wastes a download. Doing neither is the current
state and it is the worst of the three.

---

## Finding 2 (critical): every public surface is branded as somebody else's friend group

| Surface | What a stranger sees |
|---|---|
| In-game MOTD | `Homies' International Server` / `All The Mods 10 v7.1` |
| Discord server name | `Homies` |
| Discord icon | none set (blank circle everywhere it is linked) |
| Discord description | none set |
| Discord invite lands in | `#general` |

Measured:

```
$ curl -s "https://discord.com/api/v10/invites/r84QJJgUCt?with_counts=true"
  "guild": {"name": "Homies", "icon": null, "description": null,
            "vanity_url_code": null, "premium_tier": 0}
  "channel": {"name": "general"}
  "approximate_member_count": 49, "approximate_presence_count": 9
```

The word "Homies" is doing enormous damage for a single word. To the people
already in it, it is warm and accurate. To a stranger evaluating whether to
invest fifty hours in a base, it says: this is a closed friend group, you
will be the outsider, and when the friend group loses interest the server
goes away. That is the exact fear that makes people bounce off small servers,
and the name confirms it before they read a single word of the pitch.

This is also a squandered asset. "International" is buried in the middle of
that MOTD and it is the most interesting true thing about the server (see
Finding 5). The name is spending the reader's attention on the wrong half.

The blank Discord icon compounds it. Every place that invite gets posted, a
directory, a Reddit comment, a Discord embed, renders a grey circle. A server
with a 64x64 icon looks maintained; a blank one looks abandoned. This is a
five-minute fix.

Landing new arrivals in `#general` is the third compounding error. A stranger
arrives mid-conversation between people who know each other, with no idea what
the server is, how to join, or what version to install. See
`assets/discord/structure.md`.

**None of this requires the owner to stop calling it Homies.** Internally it
can stay whatever it is. The recommendation is that the *public* surfaces
carry a name a stranger can join. Options are worked through in
`assets/core-messaging.md`.

---

## Finding 3 (high): the server is capped at 20 slots while being asked to grow

```
"players": {"online": 0, "max": 20}
```

The brief describes roughly 32 players. The slot cap is 20. Two separate
problems:

1. **Hard cap.** If the community genuinely reaches 32 regulars and a good
   evening brings 20 of them on, the 21st person gets "Server full". A new
   recruit who hits that on their first attempt is gone permanently.
2. **Display cap.** Every listing site and Discord status bot renders
   `0/20` or `6/20`. A 20-slot server reads as a private server that has not
   bothered to size itself for guests. Compare the competitor set: slot caps
   of 50, 100, 200, 500 are normal even on servers with two players online.

Raising the cap is a one-line change in `server.properties`. The real
constraint is RAM and CPU headroom, which only the owner can judge, but the
cap should at least exceed the size of the existing player base. See
`QUESTIONS.md` Q3.

---

## Finding 4 (high): mcsrvstat.us cannot resolve the hostname, so some listings will show "offline"

This one is invisible without testing for it, and it is reproducible.

```
$ curl -s https://api.mcsrvstat.us/3/mc.nullsect0r.dev
  {"ip":"127.0.0.1","online":false,
   "debug":{"errors":[{"type":"ip","message":"DNS lookup failed, no IP detected."}]}}
   # three consecutive attempts, all identical
```

But the same API works perfectly when given the IP directly:

```
$ curl -s https://api.mcsrvstat.us/3/23.161.184.9
  {"online":true, "version":"1.21.1", "motd": ... }
```

And the hostname resolves fine everywhere else:

```
$ curl -s "https://dns.google/resolve?name=mc.nullsect0r.dev&type=A"     -> 23.161.184.9
$ curl -s "https://cloudflare-dns.com/dns-query?name=mc.nullsect0r.dev&type=A" -> 23.161.184.9
$ getent hosts mc.nullsect0r.dev                                          -> 23.161.184.9
$ curl -s https://api.mcstatus.io/v2/status/java/mc.nullsect0r.dev        -> online: true
```

So: the zone is served by Constellix (`ns11/21/31.constellix.com`,
`ns41/51/61.constellix.net`), the record is correct, the domain is **not**
DNSSEC-signed (no DS record at `.dev`, so this is not a validation failure),
and the failure is specific to mcsrvstat's resolver. The apex
`nullsect0r.dev` fails on mcsrvstat too, so it is the whole zone, not the
`mc` record.

Why it matters: mcsrvstat.us is the most widely embedded Minecraft status API
there is. A large number of server-list sites, Discord status bots and status
widgets call it. Anywhere that does, this server renders as **offline**, and
an offline server on a listing gets zero clicks. The server is up; the
directory says it is down.

I could not determine the cause from outside. The likely candidates are
Constellix rate-limiting or filtering queries from mcsrvstat's resolver IPs,
or a Constellix GeoDNS/ANAME configuration that does not answer for some
resolvers. Diagnosis and workaround are in `BLOCKERS.md` item 3. The cheap
workaround, if the cause cannot be found, is to list the raw IP rather than
the hostname on any site that uses mcsrvstat.

Related, smaller: **query protocol is disabled** (`"query": false`,
"Failed to read from socket"). Setting `enable-query=true` in
`server.properties` lets listing sites and bots read the live player list
rather than just a count. Minor, but free.

---

## Finding 5: "International" is real, verifiable, and currently wasted

The brief says roughly half the player base is a friend group with several
members in New Zealand, and half are people who found the server publicly.
The MOTD already says "International Server".

NZ is UTC+12/+13. Pennsylvania is UTC-4/-5. That is a 16-17 hour offset,
which means the two halves of this player base are close to antipodal. The
practical consequence is that this server plausibly has people online at
hours when a normal US-only or EU-only small server is empty.

That is a genuine differentiator and I could not find a single competitor
claiming it (see `competitors.md`). Servers in that set segment by language
and region, `[EU]`, `LATAM`, `CZ/SK`, `GER/ENG`, `PT`. Nobody is selling
*coverage across* regions.

**But it is currently unverified.** I can confirm the timezone arithmetic and
that the owner says NZ players exist. I cannot confirm that the server is
actually populated at, say, 09:00 UTC. Before this becomes the headline claim
it needs a week of evidence. The measurement method is in
`assets/systems/tracking.md` and it costs nothing: poll the status API hourly
for seven days and plot the result. If the data supports it, this is the
positioning. If it does not, the claim gets softened to something true.
See `QUESTIONS.md` Q1. Do not put a coverage claim in public copy before
the data exists.

---

## Finding 6: the server icon is the stock pack logo

The 64x64 icon returned by the ping is the standard yellow-on-black
"ALL THE MODS 10" artwork that ships with the pack.

In the multiplayer list and on every directory, this server is visually
identical to the other forty-odd ATM10 servers. There is an elaborate custom
spawn build here. A 64x64 crop of the central tower against the sky would
make the entry recognisable at a glance and costs one screenshot and one
resize. Free, ten minutes, permanently useful.

---

## Finding 7: there is no server website, and there should be a small one

`nullsect0r.dev` is live and resolves to the same IP (23.161.184.9). It is
currently a React single-page portfolio, "Ari Cummings - Full Stack Developer".

The case for a page at `mc.nullsect0r.dev` or `nullsect0r.dev/mc`:

- Directories, Discord embeds and Reddit comments all want one link. Right now
  the only link is a Discord invite, which is a commitment a browsing stranger
  may not want to make yet. A page is a zero-commitment landing spot.
- It is the one place the owner controls completely, where the version, the
  rules, the address and a live player count can always be correct. Every
  other surface goes stale.
- The two highest-friction questions, "what version do I install" and "is
  anyone actually on", can both be answered above the fold, the second of them
  live from the status API.
- Cost is genuinely near zero. Static HTML on the box already running the
  server, or GitHub Pages. The owner is a full-stack developer; this is an
  hour.

The honest counter-argument: a website does not generate traffic by itself.
Nobody searches for this server. It only converts traffic that other channels
send. So it is worth an hour, and it is worth doing before the posting starts,
but it is not worth a weekend. Spec in `assets/website-spec.md`.

---

## Finding 8: things that are genuinely good and should be said out loud

Not everything here is a problem. These are verified and they are assets:

- **The server is up and responds fast.** Pings returned cleanly on every
  attempt across the session.
- **The Pennsylvania hosting claim is true and checkable.** `23.161.184.9`
  geolocates to Sanatoga, PA, on Zayo Bandwidth (AS46887). That is a real
  datacenter on real transit, not a home connection. For a US East player
  base this is a good location, and "dedicated box in a PA datacenter" is a
  specific, falsifiable claim of the sort that builds trust.
- **A custom MOTD and a custom server icon are already configured**, so the
  owner clearly knows how to set these. The icon just needs better art.
- **The Discord invite does not expire** (`expires_at: null`), which means
  links posted in directories and old threads keep working. A surprising
  number of small servers get this wrong and leave dead invites scattered
  around the internet.
- **The Discord is already a Community server** with `COMMUNITY` and `NEWS`
  enabled, so onboarding screens, rules screening and announcement channels
  are all available at no cost and just need configuring.
