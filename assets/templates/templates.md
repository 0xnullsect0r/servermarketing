# Reusable templates

Things that will be needed more than once. Fill the brackets, do not
overthink it.

---

## Monthly "state of the server" post

For `#announcements`, and quarterly as a public post. The value is not any
single post; it is that a visible track record is *evidence of durability*,
which is the most valuable thing this server can demonstrate
(`research/competitors.md`, point 2). It compounds.

```
**State of the server, [MONTH]**

**Players:** [N] people logged in this month, [N] of them for the first
time. Average concurrent was about [N], peaking at [N] on [when].

**What changed:**
- [thing]
- [thing]

**What broke:**
- [thing, and how long it took to fix. Include this section even when it is
  embarrassing. Especially then. A changelog with no failures in it is not
  believed by anyone who has run anything.]

**Uptime:** [honest figure, or "no unplanned downtime this month" if true.
Do not invent a percentage.]

**Coming up:**
- [thing]

As always: if something is broken or annoying, say so in
#help-and-questions. I would rather know.
```

---

## Version update announcement

Post this **before** updating, not after. The audience for the last section
is everyone who has a base.

```
**Updating to All the Mods 10 [VERSION] on [DATE] at [TIME] UTC**

What this means for you:

- **You will need to update your client to [VERSION] before you can
  connect.** In your launcher, [exact instructions].
- The server will be down for roughly [N] minutes.
- A full backup is taken immediately before the update. If anything goes
  wrong we roll back.

What is new in this version: [one or two actual highlights, not a changelog
dump].

Known risks: [be specific about what might break. If mods were removed
upstream, say which ones and what happens to blocks already placed. This is
the paragraph people will remember you for, either way.]

If you hit anything odd after the update, post in #help-and-questions.
```

---

## Reply to someone asking about the server in a public thread

Short, no hard sell, no link unless links are allowed there.

```
It's a small ATM10 server, about 20-30 people, on [VERSION]. No store, no
whitelist, dedicated box, world doesn't get wiped. Not big, but it's been
running a while and someone actually maintains it.

[Discord link, or: Happy to DM you details if you want them.]
```

---

## Welcoming a new player in Discord

Do this every time. On a 30-person server it is the single highest-return
thirty seconds available, and it is also just correct behaviour.

```
Welcome @user. #start-here has the version and the address, which is the bit
people usually get wrong.

Where are you playing from, and have you played an ATM pack before?
```

---

## Checking in on someone who joined and went quiet

Only for people who joined the Discord and played at least once, never
unprompted outreach to strangers. This is retention work and it is more
valuable per minute than any acquisition work in this repo.

```
Hey, noticed you haven't been on in a bit. No pressure at all, but if
something was broken or annoying I'd genuinely like to know, it helps me fix
things for everyone else.
```

Send it once. If there is no reply, leave it. A second message is pestering.

---

## Post-mortem for a post that flopped

Add to `LOG.md`. Most posts will flop and that is normal; the point is to
learn from them in aggregate rather than to feel bad about them individually.

```
### [DATE] [CHANNEL] flop

Posted: [title/link]
Result: [numbers]
Guess at why: [rules, timing, angle, wrong audience, or just noise]
Worth retrying: [yes with changes / no]
```

After five of these, read them together. Individual flops are noise; five
flops with the same cause are a signal.
