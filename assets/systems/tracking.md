# Tracking, with free tools only

The purpose of tracking here is narrow and worth stating: **most posts will do
nothing, and the failure mode to guard against is concluding after three quiet
weeks that none of it works and stopping.** Tracking exists so that judgement
is made on data rather than on mood.

Keep it small enough that it actually gets done. An elaborate dashboard that
is abandoned in week three is worse than three numbers in a text file.

---

## 1. The seven-day timezone measurement (do this first)

This resolves **[VERIFY-1]**, which several pieces of public copy depend on.
Do not publish a coverage claim before this produces data.

`api.mcstatus.io` is free, needs no key, and returns the live player count.
Poll it hourly for seven days and plot the result by hour of day in UTC.

On the server box or any always-on machine, add to `crontab -e`:

```
0 * * * * curl -s "https://api.mcstatus.io/v2/status/java/mc.nullsect0r.dev" | python3 -c "import sys,json,time; d=json.load(sys.stdin); print(time.strftime('%Y-%m-%dT%H:00Z',time.gmtime()) + ',' + str(d.get('online')) + ',' + str(d.get('players',{}).get('online',0)))" >> ~/mcstatus.csv
```

Note: use `api.mcstatus.io`, not `api.mcsrvstat.us`. The latter cannot
currently resolve the hostname (`research/product-audit.md` Finding 4).

After seven days, average players by hour of day:

```bash
awk -F, '{split($1,a,"T"); split(a[2],b,":"); h=b[1]; sum[h]+=$3; n[h]++}
         END {for (i=0;i<24;i++){k=sprintf("%02d",i);
              printf "%s:00Z  %5.2f\n", k, n[k]?sum[k]/n[k]:0}}' ~/mcstatus.csv
```

**How to read the result honestly.** The claim being tested is "there is
usually someone on outside US evening hours". US evening is roughly
23:00-04:00 UTC. So look at **06:00-14:00 UTC**, which is New Zealand evening.

- Those hours average **1.0 or more**: the claim holds. Use the strong
  wording everywhere.
- Average **0.3 to 1.0**: soften to "there are often people on in Pacific
  hours", which is still more than any competitor claims.
- Average **under 0.3**: the claim is false. Drop it and use the fallback
  copy given throughout `assets/core-messaging.md`. Disappointing, but much
  better than publishing it and having a New Zealand player join, find an
  empty world, and leave.

Keep the cron job running afterwards. It becomes the long-run concurrency
record for free, and that is the primary success metric below.

---

## 2. The metrics that actually matter

Three numbers. Not more.

| Metric | Source | Cadence | Why |
|---|---|---|---|
| **Average concurrent players** | the CSV above | weekly | The real goal. Everything else is a proxy. |
| **Returning players after 14 days** | in-game, see below | monthly | The retention-weighted half of the goal |
| **Discord members** | Discord API, one curl | weekly | Leading indicator; moves before player counts do |

Discord members, one line:

```bash
curl -s "https://discord.com/api/v10/invites/r84QJJgUCt?with_counts=true" \
  | python3 -c "import sys,json; d=json.load(sys.stdin); print(d['approximate_member_count'], d['approximate_presence_count'])"
```

**The retention number is the important one and it takes manual effort.**
Once a month, list everyone who joined for the first time in the previous
month, and count how many logged in at least once more than 14 days after
their first login. Server logs or the player data directory will tell you.

If that number is below about a third, **the problem is the server
experience, not the marketing**, and more posting will make things worse
rather than better.

---

## 3. Attribution, which is mostly not worth doing

Knowing *which* channel sent someone is harder than it sounds and most of the
effort is wasted. Two cheap methods are worth it.

**Ask.** A "how did you find us?" question in Discord onboarding costs
nothing and gets a usable answer from most people. This is the best
attribution method available. Add it as a third onboarding question only if
you drop one of the other two, since three questions starts to feel like a
form.

**Distinct invite links.** Discord allows multiple invites to the same
channel and shows a use count for each. Make one per channel:

| Channel | Invite label |
|---|---|
| ATM Discord post | `atm-discord` |
| r/feedthebeastservers | `r-ftbservers` |
| r/allthemods | `r-atm` |
| moddedminecraftservers.com | `mms-listing` |
| Disboard | `disboard` |
| Website | `site` |

Set them to never expire, unlimited uses. Server Settings > Invites then
shows exactly which channel produced which joins, for free, forever. Worth
the fifteen minutes.

**Do not bother with:** UTM parameters (nobody clicks through a chain long
enough for them to survive), website analytics (volumes will be too small to
mean anything), or any attempt to track individuals, which is also excluded
by the brief.

---

## 4. The log

One markdown file, `LOG.md`, at the top of this repo. One line per action,
one block per week. Version controlled, free, greppable a year from now.

```markdown
## 2026-09-22
- Posted r/feedthebeastservers. Link: <url>. Title used: <title>.
- Outcome after 48h: 14 upvotes, 5 comments, 3 Discord joins (invite r-ftbservers).

## Week of 2026-09-22
- Avg concurrent (from CSV): 4.2
- Discord members: 52 (+3)
- Notes: two of the three joins installed the wrong pack version first.
  Version confusion is the top friction point. Reinforces BLOCKERS item 2.
```

That last kind of note is the most valuable output of the whole system.
Numbers tell you whether something is working. Notes tell you why.

---

## 5. Review cadence

**Weekly, five minutes.** Record the three numbers. Do not draw conclusions
from one week.

**Monthly, thirty minutes.** Look at the trend. Ask:

- Which channel produced the most joins per hour of effort spent?
- What is the 14-day retention number? If it is poor, **stop posting and fix
  the server experience instead.** More traffic into a leaky funnel makes
  things worse and burns reputation that is hard to win back.
- Is anything in the calendar skipped every month? If so, delete it from the
  calendar. A plan that is not followed should be shortened until it is,
  rather than carried around as a standing reproach.

**At 90 days.** Compare against the honest expectation in `STRATEGY.md`
section 4: 10-25 people trying the server, 3-8 becoming regulars. If the
result is in that range the plan is working, so continue. If it is far below,
the most likely causes, in order of probability, are:

1. The version gap was never closed.
2. The ATM Discord post never happened.
3. The Discord landing experience is still losing people.

Check those three before concluding the strategy was wrong.
