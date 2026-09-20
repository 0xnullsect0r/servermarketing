# Ten content ideas, with honest effort estimates

The custom spawn (floating island, central tower, elytra course, heavy modded
blockwork) is the best unexploited asset this server has. It is elaborate, it
is real, and it has apparently never been photographed. Of the 43 competitor
listings, essentially all describe themselves in adjectives. A server that
leads with a photograph of a thing someone actually built is doing something
structurally different from its entire competitive set, and it costs one
screenshot.

Effort estimates are in owner-hours and assume no prior video experience.
"Reusable" means the artefact keeps working after it is made, which is what
the brief's secondary objective asks for.

| # | Idea | Effort | Reusable | Verdict |
|---|---|---|---|---|
| 1 | Spawn screenshot set | 2h | Very high | **Do first. Everything else depends on it.** |
| 2 | Elytra course POV clip | 2h | High | **Do second** |
| 3 | Public live status page | 3h | Very high | **Do third** |
| 4 | ATM10 server tuning writeup | 4h | High | Do in month 2 |
| 5 | Custom 64x64 server icon | 0.5h | Very high | Do immediately, trivial |
| 6 | Spawn build timelapse | 8h+ | Medium | Only if someone enjoys it |
| 7 | Player base tour series | 3h each | Medium | Good, but depends on players |
| 8 | Open-source the restart/backup automation | 5h | Very high | Month 3, best long-term play |
| 9 | "State of the server" quarterly post | 1.5h | Medium | Cheap, builds durability evidence |
| 10 | Annotated spawn map | 4h | Medium | Nice, not necessary |

## The three worth doing properly

---

## Idea 1: The spawn screenshot set

**Do this first.** Six other things in this repo are blocked on it: the
Reddit build post, the directory listings, the Discord icon, the ATM Discord
post, the website, and the `#start-here` message.

### The hook

Not a caption. The image itself is the hook. The specific thing that makes
this build photographable is that it is *floating*, which means it can be
shot from below and from outside, which almost no Minecraft build can. The
underside of an island is an unusual image and unusual images stop scrolls.

### Structure: six shots

1. **The hero.** The island from outside and slightly below, at a distance,
   with sky behind it. This is the one that goes on every listing, the
   Discord icon, and the top of every post. Shoot at dawn or dusk for
   directional light.
2. **The tower, full height,** from the ground or from a hovering position,
   so the scale reads.
3. **Tower interior**, showing the modded blockwork up close. This is the
   shot that proves it is an ATM build rather than a vanilla one, and it is
   what the r/allthemods audience will actually look at.
4. **The elytra course start line**, ideally with the course visible
   receding into the distance.
5. **The underside of the island.** The most distinctive available image.
6. **A wide shot with players in it**, if you can get two or three people to
   stand around. A build with people in it reads as alive. An empty build,
   however good, reads as a ghost town, and that is the exact fear this
   server needs to dispel.

### What to capture, practically

- Render distance 16 or higher, so the background is not fog.
- **F1 to hide the HUD.** A screenshot with a hotbar and a chat log in it
  looks like a bug report. This single keystroke is the difference between
  an image that gets upvotes and one that does not.
- Turn off any shader with heavy bloom. It looks impressive in motion and
  muddy in a still.
- Time of day: dawn or dusk. Midday Minecraft light is flat.
- Shoot more than you need, at least 20, and pick 6.
- Keep the raw files. You will want different crops later.

### Where it goes

Everywhere. r/allthemods build post, the moddedminecraftservers.com listing,
the Discord icon (crop shot 2 to 64x64), `#start-here`, the website, the ATM
Discord post, and every future post for the next year.

### Effort

Two hours, once, including retakes. This is the highest return on two hours
available anywhere in this plan.

---

## Idea 2: The elytra course POV clip

### The hook

The first three seconds have to be motion. The clip that works is: launch,
immediate near-miss with the tower, then out into open sky under the island.
The hook is the near-miss. Nothing needs to be said over it.

The reason this works as content rather than as an advert is that an elytra
course is a *thing to do*, and "there is something to do here" is a more
persuasive statement than any adjective. It also implicitly communicates that
other people built it, which means other people are here.

### Structure

30 to 45 seconds. Single take, no cuts if you can manage it, because cuts in
a flight clip look like you are hiding the boring parts.

1. 0-3s: launch and the near-miss.
2. 3-25s: the run, through the tower and around the underside.
3. 25-35s: land, and the camera keeps looking at the island for a beat.

No music, or very quiet music. Minecraft's own sound is better than most
people's music choices and this audience is used to it. **No voiceover, no
text overlay, no "SUBSCRIBE".**

### What to capture

- Record with OBS at 1080p60. Free.
- Do the run ten times and keep the best one. You will crash a lot and the
  crashes are not usable, which is fine.
- Optional: one crash clip kept separately. A two-second failure clip is
  genuinely good content for the Discord and makes the place feel human.
- Record once in daylight and once at night if the build has lighting.

### Where it goes

- The Discord, `#builds-and-screenshots`, immediately.
- YouTube as a normal upload, public, mostly so it has a stable URL that can
  be embedded and linked. Do not expect YouTube views to matter.
- Attached to the ATM Discord post if that channel allows images.
- Embedded on the website.
- If, and only if, someone feels like it, a Shorts/TikTok cut. Treat that as
  a free lottery ticket, not a strategy. See `research/channels-content.md`
  for why a sustained short-form habit is not recommended.

### Effort

Two hours including the failed runs.

---

## Idea 3: The public live status page

The most reusable thing in the list, and the one that plays most directly to
the owner's actual skills.

### The hook

Not a hook in the marketing sense. This answers, permanently and without
anyone having to ask, the two questions that kill more prospective joins than
anything else:

1. **What version do I install?**
2. **Is anybody actually on?**

Question 1 is currently answered nowhere public, and getting it wrong is the
most likely reason a recruited player fails to join
(`research/product-audit.md` Finding 1). Question 2 is the thing every
skeptical reader of a small server's pitch wants to know and cannot find out
without joining a Discord.

### Structure

One page. Static HTML plus a small amount of JavaScript, served from the box
that is already running, or GitHub Pages. No framework.

Above the fold:

- Server name and one-line pitch.
- **The address, as copyable text.**
- **The exact pack version, in large type,** with a direct link to the right
  CurseForge file and one sentence on picking it in the launcher.
- **Live player count and online/offline state.**
- Next scheduled restart.
- Discord invite button.

Below the fold: the hero spawn screenshot, the 200-word pitch, the rules, and
"who runs this".

### Technical notes

- Poll `https://api.mcstatus.io/v2/status/java/mc.nullsect0r.dev` from the
  browser. It returns online state, version, player count, MOTD and the icon,
  and it works today.
- **Do not use `api.mcsrvstat.us`.** It cannot currently resolve this
  hostname (`research/product-audit.md` Finding 4).
- Cache the response for 60 seconds so the page does not hammer the API.
- **Handle the offline case deliberately.** "Offline, back shortly, restarts
  are at HH:MM and HH:MM" reads as a well-run server. A broken widget or a
  blank space reads as an abandoned one. This case will happen twice a day by
  design, so it is not an edge case.
- Host at `mc.nullsect0r.dev` on port 80/443, or `nullsect0r.dev/mc`.

### Where it goes

It becomes the single canonical link. Every listing, every Reddit post that
allows a link, the Discord, and the ATM Discord post. One URL that is always
correct, instead of a Discord invite that asks for a commitment before the
person has decided.

### Effort

Three hours for someone who does this professionally. Then essentially zero
forever.

---

## The other seven, briefly

**4. ATM10 server tuning writeup (4h, high reuse).** The r/admincraft post in
`assets/reddit/03-admincraft-technical.md`. Needs real numbers gathered
first. Builds the owner's credibility, which is the positioning.

**5. Custom 64x64 server icon (0.5h, very high reuse).** Currently the stock
ATM10 pack logo, making this server visually identical to 42 others in the
multiplayer list and on every directory. Crop the spawn tower shot. Ten
minutes, permanent effect. **Do it the same day as idea 1.**

**6. Spawn build timelapse (8h+, medium reuse).** Looks great, but it needs
Replay Mod or Axiom, a lot of rendering, and editing. Only worth it if
someone finds that fun. The flyover in idea 2 gets 80% of the effect for 25%
of the work.

**7. Player base tour series (3h each, medium reuse).** Ask a player to show
their base, record it, post it. Genuinely good: it shows other people exist,
it shows what the server looks like after fifty hours, and it makes the
featured player feel valued, which is retention work disguised as content.
Depends entirely on players being willing. **Always ask permission before
publishing anything with someone's build or username in it.**

**8. Open-source the restart and backup automation (5h, very high reuse).**
The best long-term play in the list, argued in
`research/channels-content.md`. A GitHub repo with the Crafty restart-warning
and backup scripts, written up so another ATM10 operator can use them. It
cannot be copied by the other 42 servers because almost none of them are run
by someone who could write it, and it keeps being found through search for
years. Slow, and it reaches admins rather than players. Month 3.

**9. Quarterly "state of the server" post (1.5h, medium reuse).** A short
public post: what changed, what broke, how many people played, what is next.
Posted in `#announcements` and, once there are a few, linkable as a series.
The point is not the individual post. It is that a visible track record of
quarterly posts is *evidence of durability*, which is the single most
valuable thing this server can demonstrate
(`research/competitors.md`, point 2). It gets more valuable the longer it
runs, which is the definition of a compounding asset.

**10. Annotated spawn map (4h, medium reuse).** A rendered overhead map of
spawn with labels. Nice for the website and the Discord. Genuinely useful for
new players. Not a priority.

## What to do in the first fortnight

Ideas 5, 1, 2, 3, in that order. Roughly eight hours total, and it unblocks
almost everything else in this repo.
