# Blockers: things needing owner action or access I do not have

Five items. The first four are genuinely blocking. Items 2 and 3 are
technical and I would fix them myself if I had access to the box.

---

## 1. Reddit is unreachable from my environment, so no subreddit rule is verified

**Status: blocks all Reddit posting.**

**What happened:** every route to Reddit failed. `www.reddit.com` and
`api.reddit.com` return HTTP 403, `old.reddit.com` redirects to a login wall,
the fetch tool refuses both hostnames outright, every Redlib mirror I tried
was behind an Anubis proof-of-work challenge or rate-limited, and a public
reader proxy hit a Cloudflare interstitial. Full list in
`research/00-method-and-limits.md`.

I did not attempt to defeat any of those bot challenges. Doing so to scrape a
site that is deliberately blocking automated readers is the kind of thing
that gets accounts and IPs in trouble, which is precisely what the brief
says to avoid.

**What it costs:** I have not read the current rules of r/allthemods,
r/feedthebeast, r/MinecraftBuddies, r/mcservers or r/minecraftserverlist. The
drafts in `assets/reddit/` are written conservatively and separate measured
facts from clearly labelled inference, but inference is what they are.

**What the owner needs to do:** the ten-minute checklist at the bottom of
`research/channels-reddit.md`, covering all five subreddits. Scheduled for
Tue 29 Sep in `CALENDAR.md`.

**Do not post anything to Reddit before this is done.** The specific risk is
a shadowban on `u/nullsect1r`, which is invisible to the account holder and
would cost the entire channel without anyone noticing for weeks.

---

## 2. The ATM10 version gap needs a decision, and it is the biggest one

**Status: blocks effective recruitment on every channel.**

The server runs **7.1**. CurseForge currently ships **8.1**, released
2026-08-29. That is four releases (7.2, 7.3, 8.0, 8.1) and just under three
months. Someone who reads a post, installs the pack and clicks connect gets
8.1 and cannot join. Most of them will assume the server is dead rather than
work out that they need a specific older version.

There are exactly three defensible options and only the owner can choose.

**Option A: update to 8.1.** Removes the friction entirely and gets Ad Astra,
which is a headline feature people ask about. Risk: a mid-world pack update
on a server with established bases can break things. Mitigate with a full
backup first and the announcement template in
`assets/templates/templates.md`.

**Option B: stay on 7.1 and say so loudly everywhere.** Entirely legitimate.
Protecting existing players' bases is a good reason. But it only works if
every public asset states the version prominently with instructions for
selecting it in the launcher. Draft wording for this is already in the
listing copy, the Reddit posts, the ATM Discord post and `#start-here`.
Volunteering the downside is also one of the more credible things you can do
in a recruitment post.

**Option C: update on a stated date.** Announce the date now, use it in the
copy ("we move to 8.1 on [date]"), and recruit against it. Combines most of
A's benefit with B's safety.

**What is not an option:** the current state, which is staying on 7.1
without saying so. That is the worst of the three, because it spends
recruitment effort on people who will fail to connect and never tell you why.

**Decision needed by:** Mon 21 Sep, because most of the copy has a
`[VERSION]` placeholder that cannot be filled until this is settled.

---

## 3. mcsrvstat.us cannot resolve the domain, and I cannot diagnose it from outside

**Status: will cause "offline" listings on some directories.**

Reproducible, three of three attempts:

```
$ curl -s https://api.mcsrvstat.us/3/mc.nullsect0r.dev
  {"ip":"127.0.0.1","online":false,
   "debug":{"errors":[{"type":"ip","message":"DNS lookup failed, no IP detected."}]}}
```

But the same API works fine given the IP, and every other resolver answers
correctly:

```
$ curl -s https://api.mcsrvstat.us/3/23.161.184.9                          -> online: true
$ curl -s "https://dns.google/resolve?name=mc.nullsect0r.dev&type=A"       -> 23.161.184.9
$ curl -s "https://cloudflare-dns.com/dns-query?name=mc.nullsect0r.dev&type=A" -> 23.161.184.9
$ curl -s https://api.mcstatus.io/v2/status/java/mc.nullsect0r.dev         -> online: true
```

What I established: the zone is served by Constellix
(`ns11/21/31.constellix.com`, `ns41/51/61.constellix.net`), the apex
`nullsect0r.dev` fails on mcsrvstat too so it is the whole zone rather than
the `mc` record, and the domain is **not** DNSSEC-signed (no DS record at
`.dev`), so this is not a validation failure.

**Why it matters:** mcsrvstat.us is the most widely embedded Minecraft status
API there is. Any listing site, Discord bot or status widget backed by it
will show this server as offline. An offline listing gets zero clicks. The
server is up and the directory says it is down.

**What the owner should check, in order:**

1. The Constellix dashboard, for rate limiting, query filtering, or an ANAME
   or GeoDNS/geo-proximity configuration without a global default answer.
   A geo rule that does not answer for some resolver locations would produce
   exactly this.
2. Whether Constellix is dropping queries from a particular ASN or resolver
   range.
3. Whether the zone answers correctly over TCP as well as UDP.
4. If nothing is found, consider moving DNS to a plainer provider. The zone
   is simple and nothing here needs Constellix's feature set.

**Workaround, available immediately:** use `23.161.184.9` instead of the
hostname on any listing that renders offline. Not elegant, but a listing that
says "online" beats a pretty address that says "offline". This is already
noted in `assets/listings/listings.md`.

**Related, trivial:** `enable-query=false` in `server.properties`. Setting it
true lets listing sites read the live player list rather than just a count.

---

## 4. I cannot join Discord servers, so the best channel is unverified

**Status: blocks the single highest-value post in the plan.**

The official All The Mods Discord has 177,035 members and 59,120 online, and
its own description says people go there to find a server. By measurement it
is worth more than everything else combined.

I could not join it, so I do not know whether it has a server-advertising
channel, what it is called, what the cooldown is, or whether links and images
are allowed.

**What the owner needs to do:** the six steps at the top of
`assets/discord/atm-discord-post.md`. Twenty minutes. Scheduled for Mon 28
Sep.

**Worth stating plainly:** a large official Discord's advertising channel is
where careless self-promotion gets people banned fastest, and a ban there
would cost the best available channel. Read the rules, follow the cooldown
exactly, and do not repost because the first one scrolled away.

---

## 5. Credentials and access I do not have, listed for completeness

None of these are blocking the deliverables. They are simply things I could
not do from here.

- **Server box / Crafty Controller.** So I could not read `server.properties`
  (hence Q3, Q8), check the restart schedule or backup config (Q10), or fix
  the slot cap and query setting myself.
- **The `u/nullsect1r` Reddit account.** So I could not read its post
  history, which is the best available evidence about what has already worked
  in r/allthemods.
- **The Discord server's admin settings.** So the Discord changes in
  `assets/discord/structure.md` are instructions rather than applied
  changes.
- **The game client.** So the spawn screenshots, which six other deliverables
  depend on, have to be taken by the owner. `assets/content/ideas.md` idea 1
  has the shot list and the settings.
- **Web hosting for `nullsect0r.dev`.** The status page is a spec
  (`assets/website-spec.md`), not a deployment.
