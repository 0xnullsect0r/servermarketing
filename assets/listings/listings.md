# Server list listings

## Which sites, in order

Full reasoning in `research/channels-server-lists.md`. The short version is
that I tested the general lists rather than assuming, and their "Modded"
categories contain 0-1 mentions of All the Mods against 2-34 mentions of
Cobblemon. They are Pokemon categories wearing a modded label.

**Tier 1, do this (about 30 minutes):**

| Site | Free tier | Why |
|---|---|---|
| **moddedminecraftservers.com** | Free listing, free voting, optional paid "highlighted" tier which we ignore | The only directory where the ATM10 category is genuinely populated (43 servers). Listed alongside a set that is two-thirds dead, a live well-described server stands out. |

**Tier 2, do once then ignore (about 20 minutes):**

| Site | Free tier | Why |
|---|---|---|
| **topg.org** | Free listing, vote-ranked | The only general list with any ATM10 presence at all (4 mentions, supports an `atm10` tag). Submit, tag, forget. Do not chase votes. |

**Tier 3, explicitly skipping:** minecraftservers.org, minecraft.buzz,
mcserverlist.net, mc-servers.com, minelist.io. Zero ATM presence,
vote-ranked in a way that structurally excludes a 20-slot server, and the
expected return is approximately zero for an hour of forms plus a permanent
obligation to nag players to vote.

**planetminecraft.com:** unranked, because I could not read it (Cloudflare
blocked me). My prior is that it belongs in tier 3. It costs ten minutes to
check by hand: search the site for "All the Mods" and see whether anything
real comes back. `QUESTIONS.md` Q6.

## Critical: do not submit the hostname to any site that uses mcsrvstat.us

`api.mcsrvstat.us` **cannot currently resolve `mc.nullsect0r.dev`**. It fails
on three of three attempts while resolving the raw IP fine and while every
other resolver on the internet answers correctly
(`research/product-audit.md` Finding 4). mcsrvstat is the most widely embedded
Minecraft status API there is, so any listing backed by it will render this
server as **offline**, which is worse than not being listed.

**Before submitting anywhere, test it.** Enter the address into the site's
preview if it has one, or check the listing an hour after submitting. If it
shows offline, edit the listing to use `23.161.184.9` instead of the
hostname. Not elegant, but a listing that shows "online" beats a pretty
address that shows "offline".

Better: fix the underlying DNS issue first. `BLOCKERS.md` item 3.

---

## Short description

For fields with a tight limit. **147 characters**, which fits the common
150-character cap and most meta-description limits:

```
Small All the Mods 10 server. US and NZ players so it's rarely empty. Dedicated box, scheduled restarts, real backups, no store, world never wiped.
```

**Under 100 characters** (95), for the tightest fields:

```
Small ATM10 server, US+NZ players, dedicated box, scheduled restarts, no store, no world wipes.
```

**Under 80 characters** (75), for taglines:

```
Small ATM10 server run properly. Two hemispheres, no store, no world wipes.
```

If **[VERIFY-1]** fails, drop the US/NZ clause:

```
Small All the Mods 10 server on a dedicated box. Scheduled restarts with warnings, tested backups, no store, world is never wiped. Run by a developer.
```

---

## Long description

For sites with a full description field. Plain text with light formatting,
because most listing sites either strip markdown or render it badly.

```
Homies' International is a small All the Mods 10 server for people who want
their base to still be there in six months.

WHAT IT IS

About 20 to 30 players on ATM10 [VERSION], Minecraft 1.21.1, NeoForge. It
started as a group of friends, several of whom live in New Zealand, and
roughly half the people on it now found it on their own and stayed. The
practical effect of that split is that there is usually someone online
outside US evening hours, which is unusual for a server this size.

HOW IT IS RUN

It runs on a dedicated machine in a Pennsylvania datacenter. Not a home PC,
not shared hosting.

- Restarts twice a day on a schedule, with countdown warnings in chat
- Backups are real and have actually been restored from
- The world is not wiped
- No store, no ranks, no crates, no keys, nothing to buy, and none planned
- No playtime requirements, and nothing is reclaimed if you go inactive

It is run by one person who writes software for a living, so a bug report
goes to the person who can fix it rather than into a ticket queue.

RULES

Be decent to people. Do not take other people's things. That is the whole
list.

SPAWN

A custom build: a floating island with a large central tower, and an elytra
course that runs through the tower and around the underside of the island.

WHAT IT IS NOT

Not big, not a network, not a hardcore progression server. If you are
looking for two hundred concurrent players, this is not that.

Address: mc.nullsect0r.dev
Discord: https://discord.gg/r84QJJgUCt
```

**Fill in `[VERSION]` honestly.** If still on 7.1 while CurseForge ships 8.1,
add this line directly under the version, because someone finding out after a
3GB download is a lost player and someone finding out here is a filtered one:

```
Note: we are on 7.1, not 8.1. You will need to select that version in your
launcher rather than taking the latest.
```

---

## Tags and categories

Use every relevant tag a site offers, since tag pages are how modded players
actually browse. In rough priority order:

**Essential:** `all the mods`, `all the mods 10`, `atm10`, `modded`,
`modpack`, `neoforge`, `1.21.1`, `java`

**Strong fit:** `smp`, `survival`, `pve`, `no whitelist`, `no pay to win`,
`nopvp` (if accurate, see `QUESTIONS.md` Q8), `small community`, `18+`
(if the owner commits to it), `english`

**Regional:** `usa`, `us east`, `oceania`, `new zealand`, `international`.
Include the Oceania and NZ ones only if **[VERIFY-1]** holds, but if it does,
these are valuable: the competitor set segments regionally and nobody claims
more than one region.

**Category selection:** pick `Modded` or `Modpack` where offered, `Survival`
or `SMP` second. Do not pick `Vanilla`, `Minigames`, `Factions`, `Prison`,
`Skyblock` or `Economy`, even where a loose argument could be made. Wrong-tag
traffic is worse than no traffic, because it produces joins from people who
leave immediately, which is the opposite of the retention-weighted goal.

**Do not tag:** `pvp` unless it is true, `lifesteal`, `anarchy`, `hardcore`,
`crossplay` (this is Java only), `bedrock`.

---

## Submission checklist

For each site, once:

- [ ] Address: test whether the site resolves `mc.nullsect0r.dev`. If it
      shows offline, use `23.161.184.9`.
- [ ] Upload a **custom banner or icon**, not the stock ATM10 pack logo. The
      current server icon is the pack's default artwork, which makes this
      server visually identical to 42 others
      (`research/product-audit.md` Finding 6). A 64x64 crop of the spawn
      tower takes ten minutes and is permanently useful.
- [ ] Short description in the tagline field, long description in the body.
- [ ] Every relevant tag from the list above.
- [ ] Discord invite link (it does not expire, so it is safe to publish).
- [ ] Set the version field accurately, including the 7.1 caveat.
- [ ] After an hour, load the public listing page and confirm it shows
      **online** with the right player count. If it does not, fix it now
      rather than leaving a dead listing up.
- [ ] Record the URL of your listing in `assets/systems/tracking.md` so you
      can check on it later.

## Maintenance

Near zero, which is the point. Revisit only when:

- The pack version changes. **Update every listing the same day**, because a
  wrong version on a listing sends people to a failed connection.
- The slot cap changes.
- **[VERIFY-1]** resolves and the description needs the timezone claim added
  or removed.

Set a calendar reminder for one review every 90 days. That is the entire
ongoing cost of this channel.
