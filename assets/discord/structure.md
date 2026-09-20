# The server's own Discord: structure, roles, onboarding, and copy

This is the highest-value item in `assets/` after the product fixes, because
every other channel funnels here and the funnel currently leaks. Unlike a
post, this works on every visitor forever.

## Current state, measured 2026-09-20

```
$ curl -s "https://discord.com/api/v10/invites/r84QJJgUCt?with_counts=true"
  guild name:  "Homies"
  icon:        null
  description: null
  vanity_url:  null
  members: 49, online: 9
  invite lands in: #general
  features: COMMUNITY, NEWS, SOUNDBOARD  (so onboarding tools are available)
  widget: disabled
```

## Do these five things first, they take fifteen minutes

Before any restructuring, these are the highest-return changes and none of
them takes longer than five minutes.

1. **Set a server icon.** Currently blank, so every embed and directory
   listing renders a grey circle, which reads as abandoned. Use a crop of the
   spawn tower.
2. **Set the server description.** Server Settings > Overview. Discord shows
   this in previews and directories. Use the 147-character short description
   from `assets/listings/listings.md`.
3. **Enable the server widget.** Server Settings > Widget. One toggle. It
   lets external sites and bots show "9 online now", which is the social
   proof a browsing stranger actually wants.
4. **Change the invite landing channel** from `#general` to a
   `#start-here` channel (created below). Server Settings > Invites, or just
   generate the new invite from the right channel.
5. **Decide the name question** (`assets/core-messaging.md`). If going with
   "Homies' International", rename now so the rest of the setup is
   consistent.

## Channel structure

Deliberately small. A near-empty 30-channel Discord looks dead; a busy
8-channel one looks alive. The same conversation spread across twelve
channels reads as a ghost town, and that is the single most common mistake
small server Discords make.

```
INFORMATION  (read-only for everyone)
  #start-here        <- invites land here
  #rules
  #announcements     (NEWS channel, so other servers can follow it)
  #server-status     (restart notices, downtime, version changes)

COMMUNITY
  #general
  #builds-and-screenshots
  #help-and-questions
  #suggestions

VOICE
  General
  AFK
```

That is nine channels. Add more only when an existing channel is visibly too
busy, never in anticipation.

**Notes on specific channels:**

- `#start-here` is the whole conversion surface. Everything a stranger needs
  is in one pinned message, below.
- `#server-status` is a differentiator in itself. Posting "restarting in 5"
  and "back up, took 90 seconds" is public evidence that the server is
  actively operated, which is the core claim of the positioning. Automate it
  from Crafty if possible; post manually if not.
- `#help-and-questions` separated from `#general` so that a new player's
  question does not get lost in conversation, and so the owner can see at a
  glance whether anything is unanswered. **An unanswered question in here is
  the most expensive thing that can happen in this Discord.**
- `#builds-and-screenshots` feeds the content pipeline. Players post
  screenshots, and those screenshots become Reddit posts and listing images
  later, with permission.

## Roles

Keep it to four. Role sprawl is another thing that makes small servers look
like they are pretending to be big.

| Role | How it is given | Purpose |
|---|---|---|
| `@Owner` | one person | Clarity about who to ask |
| `@Player` | automatically on completing onboarding | Unlocks the community channels |
| `@Visitor` | default on join | Can see the information channels only |
| `@Announcements` | self-assigned, opt-in | Pingable for restarts and downtime |

**Do not create donor, VIP, or paid ranks.** There is no store and there
should be no cosmetic hierarchy that hints at one. Also do not create
activity-based ranks, which create an obligation to keep playing, which is
the opposite of what Segment B wants.

The `@Visitor` to `@Player` split is worth the small complexity: it means the
public channels a stranger first sees are curated, and it gives a natural
moment of welcome when someone becomes a Player.

## Onboarding flow

The Discord already has `COMMUNITY` enabled, so Discord's own Onboarding and
Rules Screening features are available for free. Use them.

**Rules Screening** (Server Settings > Membership Screening): people must
tick that they have read the rules before they can talk. Set the rules to the
short list below.

**Onboarding** (Server Settings > Onboarding): ask exactly two questions. One
is tolerable, three is a form.

Question 1: *"Where are you playing from?"* Options: `Americas`,
`Europe/Africa`, `Asia/Pacific`. Assigns a timezone role.

Why this question specifically: it is genuinely useful (people can see who
overlaps with them), it is the only question that directly supports the
positioning, and it generates the data needed to keep **[VERIFY-1]** honest
over time.

Question 2: *"Have you played an All the Mods pack before?"* Options:
`Yes, plenty`, `A bit`, `First time`. No role needed, or a `@New to ATM` role
so people know who to help.

Then `@Player` is granted and the community channels open up.

---

## Copy: `#start-here`

Pin this. It is the single most important piece of writing in the whole repo,
because it is what a stranger reads at the moment they are deciding.

Fill in `[VERSION]` honestly and keep it current.

```
Welcome. This is the Discord for a small All the Mods 10 server.

Everything you need is in this message.

**How to join the server**

1. Install All the Mods 10 version [VERSION] from CurseForge, the FTB app,
   or Prism. You need that exact version, not the latest one.
2. Add the server: mc.nullsect0r.dev
3. Say hello in #general so we know who you are. Not a requirement, just
   nice.

There is no whitelist and no application.

**What this server is**

About 20 to 30 people. It started as a group of friends, several of whom are
in New Zealand, and roughly half the people here now turned up on their own
and stayed. Because of that split there is usually someone online outside US
evening hours.

It runs on a dedicated machine in a Pennsylvania datacenter. It restarts
twice a day on a schedule, with countdown warnings in chat. Backups are real
and have been restored from. The world does not get wiped.

There is no store. No ranks, no crates, nothing to buy, and none planned.

**What this server is not**

It is not big, and it is not a network. If you are looking for two hundred
concurrent players this is not that. There are quiet stretches, usually
mid-week, where it is one or two people.

**Rules**

Be decent to people. Do not take other people's things. Full version in
#rules, but that is genuinely the substance of it.

There are no playtime requirements. If you disappear for a month your base
will still be there.

**If something breaks**

Post it in #help-and-questions and tag me. I run this, I write software for
a living, and I would much rather know.

**Spawn**

There is a floating island with a tower and an elytra course through the
middle of it. Screenshots in #builds-and-screenshots. The underside of the
island is the good part.
```

### The version paragraph, if still on 7.1

Add this directly under step 1. It is the most useful paragraph in the
message, because the alternative is someone downloading 3GB and failing to
connect.

```
**Important about the version:** we are on 7.1, and CurseForge will hand you
8.1 by default. In the launcher, open the version dropdown and pick 7.1
specifically. I am holding off on 8.x until I am confident it will not break
people's existing bases. If you get "outdated server" or a mod mismatch,
this is why.
```

---

## Copy: `#rules`

Short on purpose. A long rule list on a 30-person server signals past drama
and invites rules-lawyering.

```
**Rules**

1. Be decent to people. Disagreements are fine, being unpleasant is not.
2. Do not take other people's things, and do not break their builds. If you
   want something from someone's base, ask them.
3. Do not grief spawn or the elytra course.
4. No slurs, no harassment, no bigotry. This one is not negotiable and there
   is no warning.
5. Client mods that give you an unfair advantage (x-ray, auto-clickers,
   cheat clients) are not allowed. Performance mods, minimaps and QoL mods
   are completely fine.
6. If someone asks you to stop doing something, stop doing it.

There are no playtime requirements. Nothing is reclaimed if you go inactive.
You do not need to tell anyone you are taking a break.

**Enforcement:** I will talk to you first. I have no interest in banning
people over misunderstandings. Rule 4 is the exception.

**Reporting:** DM me. It stays between us.
```

---

## Copy: welcome message

Discord's built-in join message is noise. Turn it off (Server Settings >
Overview > System Messages) and have the owner or a bot post this in
`#general` instead. A real greeting from a person is worth far more than
"X just joined" on a server this size.

```
Welcome @user. Everything you need to actually join is pinned in #start-here,
including which version to install, which is the bit people usually get
wrong.

Where are you playing from, and have you played an ATM pack before?
```

The question at the end is doing real work. A welcome message that ends in a
statement gets no reply and the person lurks and leaves. One that ends in an
easy question gets an answer, and someone who has spoken once is far more
likely to speak again.

---

## Things not to do

- **Do not add a levelling bot.** It manufactures fake activity and creates
  an obligation to keep chatting, which Segment B specifically does not want.
- **Do not add six utility bots.** A status bot and maybe a backup
  notification bot. That is it.
- **Do not create channels in anticipation of growth.** Empty channels are
  the clearest possible signal that a community is dying.
- **Do not set up an application process.** No whitelist means no
  application. Every extra step between reading the pitch and being in the
  world loses people, and at this size the filtering is not worth the loss.
- **Do not auto-DM new joiners.** It reads as a bot, and the brief's
  constraint on unsolicited contact points the same way.
