# Website spec

## Should there be one? Yes, and it should be small.

The case, in short: directories, Discord embeds and Reddit comments all want
one link, and right now the only link is a Discord invite, which asks a
browsing stranger for a commitment before they have decided anything. A page
is a zero-commitment landing spot, and it is the one surface the owner fully
controls where the version and the player count are always correct.

The honest counter-argument, which should keep the scope small: **a website
generates no traffic on its own.** Nobody searches for this server. It only
converts traffic that other channels send. So it is worth an hour or three
before the posting starts. It is not worth a weekend, and it is definitely
not worth a framework.

## Where

`mc.nullsect0r.dev` over HTTPS is the best option: it is the address people
already type, so someone who pastes it into a browser out of curiosity lands
somewhere useful instead of getting a connection error.

`nullsect0r.dev/mc` also works and may be easier given the existing React
app. Either is fine. Do not buy a domain; the constraint is zero spend and
there is no need.

Note the apex and the `mc` subdomain both already resolve to 23.161.184.9, so
this is a webserver config question, not a DNS one.

## What goes on it

One page. No framework, no build step, no CMS. Static HTML and a small script.

### Above the fold, in this order

1. **Server name** and the one-line pitch from `assets/core-messaging.md`.
2. **The address as copyable text.** A click-to-copy button if it is easy,
   plain monospace if not.
3. **The exact pack version, in large type.** With a direct link to the
   correct CurseForge file and one sentence about selecting it in the
   launcher. This is the most important element on the page. Getting the
   version wrong is the most likely reason a recruited player fails to join
   (`research/product-audit.md` Finding 1).
4. **Live status:** online/offline, current players, slots.
5. **Next scheduled restart**, in the visitor's local time if that is easy,
   UTC if not.
6. **Discord invite button.**

### Below the fold

7. The hero spawn screenshot, full width.
8. The 200-word pitch.
9. The rules, verbatim from `assets/discord/structure.md`.
10. "Who runs this", two sentences, with the owner's actual name or handle.
    This is a differentiator, not a formality: a named accountable person is
    exactly what the audience is looking for.
11. The remaining spawn screenshots, as a simple grid.

## The live status widget

```js
const API = "https://api.mcstatus.io/v2/status/java/mc.nullsect0r.dev";
```

Returns `online`, `players.online`, `players.max`, `version.name_clean`,
`motd`, and the server `icon` as a data URI. All of it verified working on
2026-09-20.

**Do not use `api.mcsrvstat.us`.** It cannot currently resolve this hostname
(`research/product-audit.md` Finding 4).

Implementation notes:

- Cache for 60 seconds client-side. Do not poll on a tight loop.
- **Handle the offline state deliberately.** The server restarts twice a day
  by design, so this is a normal state, not an edge case. Render something
  like *"Offline right now. Scheduled restarts are at HH:MM and HH:MM UTC and
  take about a minute."* That reads as a well-run server. A broken widget or
  a blank space reads as an abandoned one.
- **Handle the API being down too.** If the fetch fails, show the address and
  the version and hide the status block entirely. Never show a spinner that
  runs forever, and never let a failed fetch blank the page.
- Read the version from the API rather than hardcoding it, so the page cannot
  go stale when the pack is updated. Print `version.name_clean` for the
  Minecraft version, but the *pack* version has to be maintained by hand
  since the ping does not expose it. Keep it in one constant at the top of
  the file with a comment saying to update it on every pack change.

## What not to build

- No player list, no leaderboard, no live map. Dynmap on an ATM10 server is a
  meaningful performance cost for very little return.
- No forum, no account system, no application form.
- No newsletter signup.
- No analytics. Volumes will be far too small to learn anything, and it is
  one more thing to maintain.
- No React. This is a page, not an app. The existing portfolio being React is
  not a reason for this to be.

## Effort

Three hours for someone who does this professionally, then essentially zero
forever except updating the pack version constant.

## Maintenance trigger

**Every pack version change, update the constant the same day.** A website
advertising the wrong version is worse than no website, because it is
authoritative-looking and wrong.
