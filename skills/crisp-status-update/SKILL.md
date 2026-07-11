---
name: crisp-status-update
description: >
  Write a status update with a hard-defined state color, the delta since
  last update, owned blockers, and a dated next milestone. Use when the
  user asks to write a status update, a weekly project update, or asks
  "what do I report on this project".
license: MIT
metadata:
  version: "1.0"
  tier: S
  provenance: sanitized from the launch command board practice of a venture-backed software company
---

# Crisp Status Update

Five lines. A status update that takes 3 minutes to read gets skimmed,
and skimmed yellow becomes surprise red.

## The format

1. **State:** green, yellow, or red, by definition, not by mood.
2. **Delta:** what changed since the last update. If nothing changed,
   say "no movement" and why. Silence is not a delta.
3. **Blockers:** each with a named owner and the unblock being asked for.
   A blocker without an owner is an excuse with formatting.
4. **Next milestone:** one milestone, one date.
5. **Ask:** the single thing the reader can do, or "none".

## State definitions

- **Green:** next milestone on date, no unowned blockers.
- **Yellow:** milestone at risk up to 1 week, or a blocker unowned for
  1 business day.
- **Red:** milestone slipping more than 1 week, or a blocker unowned for
  more than 2 business days. Red requires the recovery line: new date and
  what changed to make it real.

## If/then rules

- If the update is yellow 3 weeks running → it is red. Chronic yellow is
  red with better manners.
- If the milestone date moved → state the old date and the new date side
  by side. Dates that drift silently train readers to ignore dates.
- If there is no ask 4 updates running → confirm the reader list still
  needs this update at all.

## Worked example (real math)

Week 6 of an 8-week migration. Old milestone: cutover May 20. A vendor
API limit surfaced, cutover now May 29, a 9-day slip. 9 days > 1 week,
so the state is red, not yellow. Going red means updating ALL affected
fields together: the state color, the milestone line showing May 20
struck through beside May 29, the blocker row naming the vendor contact
and the quota increase asked for, and the ask line requesting an
escalation email from the sponsor. A red update still showing the old
date is two updates fighting in one message.

## Validation (definition of done)

- [ ] State matches its definition, not the author's optimism
- [ ] Delta names what changed or says "no movement" with a reason
- [ ] Every blocker has a named owner and a requested unblock
- [ ] Exactly one next milestone with a date; slips show old and new dates
- [ ] Red updates carry a recovery line

## Adapting this to your company

Swap: the 1-week yellow band, the 3-yellows rule, the cadence. Keep:
defined colors, deltas over summaries, owned blockers, dated milestones.
