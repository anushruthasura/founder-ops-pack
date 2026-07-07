---
name: lifecycle-email-orchestrator
description: Run lifecycle and onboarding email programs on the send-ledger rule - max one automated email per person per ~48 hours across ALL streams - with a strict definition of genuine engagement. Use for onboarding, re-engagement, and usage-based lifecycle email.
---

# Lifecycle Email Orchestrator

Lifecycle email operations, sanitized from a production 3-stream program
(onboarding, re-engagement, threshold alerts). Its load-bearing rule is a
ledger, not a template.

## THE rule: the send-ledger

One ledger records every automated email to every person across ALL streams.
Before any stream sends anything: check the ledger; if the person received
ANY automated email in the last ~48 hours, this send WAITS (or is skipped if
it will be stale by then - a "your usage is spiking" email three days late
is worse than no email).

Streams designed independently are individually reasonable and collectively
harassment. The person who hits onboarding day-3 + a usage threshold + a
re-engagement trigger in one week receives ONE email per 48h window, best
send wins - not three emails on Tuesday. Priority when sends collide:
threshold alerts > onboarding > re-engagement (urgency decays in that order).

## Rule 2: "genuine engagement" excludes machine noise

Every stream branches on engagement, so the definition must be strict:
a genuine engagement is a human action - a reply, a meaningful product action,
a click into the product followed by activity. It EXCLUDES: auto-seeded
events (accounts created by your own provisioning), bot/preview opens
(email scanners open everything), and your own team's internal testing.
The production lesson: auto-seeded activity once made dormant accounts look
alive, which suppressed the re-engagement stream exactly for the accounts
that needed it. Whatever your equivalent of "auto-seed" is - find it and
exclude it before trusting any engagement branch.

## Rule 3: every stream has an exit

Each stream defines its exit conditions up front: goal reached (activated,
returned, topped up), explicit opt-out, or terminal silence (N sends, zero
genuine engagement -> stop; more email is not the answer). A stream without
an exit is a drip that eventually lands someone in the harassment zone.

## If/then

- If two streams want the same person in one window -> ledger picks by
  priority order; the losing send re-evaluates at its next eligibility, and
  skips itself if now stale.
- If a re-engagement email gets a genuine engagement -> the person exits
  re-engagement THAT moment; nothing else in that stream's queue fires.
- If engagement rate on a step drops below half its trailing average ->
  pause the step (not the stream) and inspect: usually a broken link, a
  stale claim, or a new bot filter - not suddenly-worse copy.
- If someone replies to ANY automated email -> all streams pause for them
  until a human has responded. A reply converts the relationship from batch
  to conversation; automation that talks over the human response is the
  fastest trust-killer in the whole program.

## Escalation

- Any person shows 3 automated sends inside 7 days in the ledger -> the
  collision logic has a bug; freeze all streams for that person, audit
  same-day. This is the alarm the ledger exists to make possible.
- Unsubscribe rate >0.5% on any step -> pull the step for rewrite.

## Worked example

Monday. Maria signed up 3 days ago (onboarding step 2 due), her project
crossed a usage threshold Sunday (alert due), and she was dormant last
month so re-engagement had her queued. Ledger check: last automated email
Friday 09:00. All three want Monday. Priority: threshold alert sends Monday
09:05 ("you're at 80% of your credits - here's what happens next"). Ledger
stamps Monday. Onboarding step 2 re-evaluates Wednesday 09:05 (48h clear):
still relevant -> sends. Re-engagement re-evaluates Friday: but Maria
clicked into the product Tuesday and ran a real workflow (genuine - human
action, not a seed) -> exit condition met, re-engagement dequeues without
sending. Total: 2 emails, both wanted, 4 days apart. Without the ledger:
3 emails Monday, and the one that mattered buried.

## Definition of done

- [ ] One ledger covers ALL streams; no stream sends without checking it
- [ ] 48h window enforced; collisions resolved by written priority order
- [ ] Genuine-engagement definition written, with YOUR auto-noise exclusions
- [ ] Every stream has exits: goal / opt-out / terminal-silence cap
- [ ] Reply anywhere pauses everything for that person until human response
- [ ] Ledger can answer "what did we send this person in the last 30 days" in one query

## Anti-patterns

- **Per-stream frequency caps.** "Each stream max 1/week" still lands 3 emails
  in one Tuesday when three streams fire. The cap must be per-PERSON across
  ALL streams - that's why it's one ledger, not three counters.
- **Trusting raw engagement events.** Opens are bots, seeds are your own
  provisioning, clicks include scanners. Every engagement branch built on
  unfiltered events optimizes for the wrong people - or suppresses the
  stream exactly where it's needed (the production auto-seed lesson).
- **Streams without exits.** The re-engagement drip that never concludes is
  how a dormant user's last memory of you becomes email #9 of a sequence
  they never read.
- **Automation answering over humans.** The reply-pauses-everything rule has
  no exceptions. One automated email sent after a human replied undoes a
  quarter of trust-building.

## Setup (first run, ~1 hour)

1. Build the ledger first - before any stream. Minimum schema:
   `person | stream | template | sent_at`. One query must answer
   "last automated send to X across everything".
2. Write your genuine-engagement definition, starting from the exclusions:
   list every machine source that generates engagement-shaped events in
   your stack (provisioning, monitors, internal test accounts, mail scanners).
3. Define each stream on one page: trigger, steps, exits, priority rank.
   A stream that can't fit on a page will misfire in ways you can't debug.
4. Dry-run one week: log what WOULD send, audit collisions by hand. The
   dry-run always finds a collision you didn't design for.

## Swappable parameters

- Window: `~48 hours` -> your tolerance (48-72h typical; under 24h only for transactional)
- Priority order: alerts > onboarding > re-engagement -> your streams
- Terminal silence: `N sends, zero engagement` -> your N (3-5 typical)
- Staleness: skip-if-stale definitions per stream -> your content's shelf life
