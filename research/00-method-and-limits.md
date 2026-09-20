# Research method, and what I could not check

Date of research: 2026-09-20. Everything below was gathered in one session from a
datacenter IP. Where a number is quoted, the command that produced it is shown so
the owner can re-run it and get a current answer.

## What I could reach

| Source | Reachable | Used for |
|---|---|---|
| `api.mcstatus.io`, `api.mcsrvstat.us` | yes | live server ping, MOTD, slots, icon, version |
| Discord API (`/api/v10/invites/<code>?with_counts=true`) | yes | real member and presence counts for any public invite |
| `moddedminecraftservers.com` | yes | the ATM10 competitor set (3 pages, ~45 servers) |
| `curseforge.com` (via WebFetch) | yes | pack download count, version release dates |
| `minecraftservers.org`, `minelist.io`, `mc-servers.com`, `topg.org`, `minecraft.buzz`, `mcserverlist.net` | yes | testing whether general lists carry ATM servers at all |
| DNS over HTTPS (Google, Cloudflare) | yes | verifying the hostname resolves |
| `ipinfo.io` | yes | verifying the Pennsylvania hosting claim |

## What I could not reach, and what that costs

**Reddit is completely inaccessible from this environment.** This is the single
biggest gap, because Reddit is the channel the brief cares most about.

Every route was tried and failed:

- `www.reddit.com/r/<sub>/about/rules.json` -> HTTP 403 (blocked page HTML)
- `old.reddit.com/...` -> 302 to `/login/?reason=lor2`, i.e. login required
- `api.reddit.com/...` -> HTTP 403
- The WebFetch tool -> "unable to fetch from www.reddit.com" and the same for
  `old.reddit.com`; the search tool refuses `reddit.com` as a domain filter
  outright ("not accessible to our user agent")
- Redlib / libreddit mirrors (`redlib.privacyredirect.com`, `safereddit.com`,
  `redlib.perennialte.ch`, `redlib.freedit.eu`, `l.opnxng.com`, and others)
  -> Anubis proof-of-work bot challenges, 403s, or 429s
- A public reader proxy -> Cloudflare interstitial

I did not attempt to defeat any of these bot challenges. Solving a
proof-of-work challenge to scrape a site that is deliberately blocking
automated readers is exactly the kind of thing that gets an account or an IP
in trouble, which is the opposite of the brief.

**Consequence, stated plainly:** I have not read the current rules of
r/allthemods, r/feedthebeast, r/MinecraftBuddies, r/mcservers or
r/minecraftserverlist with my own eyes. The Reddit drafts in `assets/reddit/`
are therefore written to a deliberately conservative standard, and every one
of them ships with a rule-verification checklist that takes about ten minutes
in total to work through. See `BLOCKERS.md`, item 1. Do not post any of them
before doing that check. Subreddit rules change, and a rule I inferred is not
a rule I read.

**Also blocked:** `disboard.org`, `planetminecraft.com`, `minecraft-server-list.com`,
`topminecraftservers.org`, `top.gg`, `discord.me`, `minecraftforum.net`,
`curseforge.com` via plain HTTP (Cloudflare). Where these mattered I used
search results or the platform's own API instead, and I have said so inline.

## A note on source quality

Search results for anything shaped like "how to promote a Minecraft server"
are almost entirely SEO content produced by companies selling server hosting,
Discord growth bots, or marketing services. I have not cited any of it as
evidence for a claim about what works. Where I make a claim about what works,
it rests on one of:

1. A number I measured directly (a player count, a member count, a ping).
2. The platform's own stated rules.
3. An observation about the competitor set that anyone can reproduce.

Where I have none of those three, I say I am uncertain and name what would
resolve it. Those are collected in `QUESTIONS.md`.
