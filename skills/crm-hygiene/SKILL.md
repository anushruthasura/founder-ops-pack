---
name: crm-hygiene
description: >
  Keep the CRM true with a weekly reconciliation sweep: stage-duration
  stall flags, collision detection, duplicate guards, and a stale-response
  sweep. Use when the user asks to clean up the CRM, fix pipeline data,
  find stalled or double-worked deals, or trust their forecast again.
license: MIT
metadata:
  version: "1.0"
  tier: M
  provenance: sanitized from the outbound engine reconciliation jobs of a venture-backed software company
---

# CRM Hygiene

The CRM is only the source of truth if something reconciles it against
reality on a schedule. Left alone, it drifts toward fiction at roughly
the speed of one quarter.

## The weekly sweep (four checks, same order)

1. **Stage-duration stalls.** Every stage has a max expected duration.
   Any deal over its limit gets flagged with days-over. "At risk" is a
   time-in-stage number, not a gut feeling.
2. **Collision detection.** One prospect being worked by two sequences or
   two owners is a collision. Pause the newer touch the same day; nothing
   reads worse than two people from the same company in one inbox.
3. **Duplicate guard.** Match on email domain plus name tokens, not exact
   email. Merge duplicates before they split the activity history.
4. **Stale-response sweep.** Any thread where THEIR last reply is newer
   than YOUR last touch by 7+ days: draft the follow-up or mark the deal
   dark. An unanswered buyer reply is the most expensive silence in the
   pipeline.

## Field rules

- Every deal: named owner, next step with a date, and a close date that
  has been updated in the last 30 days.
- Close dates in the past on open deals are lies. The sweep resets them
  with a note, and repeated offenders surface in the Friday digest.
- ID reconciliation runs weekly: CRM records against the sequencer and
  the calendar, catching records that lost their join keys.

## If/then rules

- If a deal has no next-step date → it is not forecastable; it drops from
  the weighted pipeline until it has one.
- If a deal is 2x over its stage limit → owner explains in the Friday
  digest: close it, move it, or state the real blocker.
- If the same account shows 3+ duplicate records in a month → the intake
  form is broken; fix the source, not just the merges.

## Worked example (real math)

Friday sweep on a 78-deal pipeline. Stage limits: discovery 14 days,
evaluation 21, proposal 14, negotiation 10. The sweep flags 9 stalls, 2
of them at 2x (a proposal at 31 days, an evaluation at 44). One collision:
an inbound SDR sequence touched an account the AE emailed Tuesday; the
sequence is paused same day. Duplicate guard merges 3 records on one
domain, and merging means updating ALL affected fields together: activity
history consolidated to one record, the owner field resolved to one name,
the sequencer's contact ID repointed, and the weighted pipeline recounted
(it drops $18,000 because two of the merged records each carried the same
$18,000 opportunity). Stale-response sweep finds 4 threads with buyer
replies 7+ days unanswered: 3 get drafted follow-ups, 1 is marked dark.
Weighted pipeline after the sweep: $612,000 down from $665,000. The
forecast shrank and became true.

## Escalation

The sweep output is a Friday digest to the pipeline owner: stalls with
days-over, collisions caught, merges, stale threads. Deals flagged 3
consecutive weeks go to the deal review, with the flag history attached.

## Validation (definition of done)

- [ ] All four checks ran, in order, this week
- [ ] Every stall flag shows days-over-limit; every 2x stall has an owner response
- [ ] Zero active collisions; zero unmerged duplicates on matched domains
- [ ] Zero buyer replies older than 7 days without a follow-up or a dark mark
- [ ] Every open deal has an owner, a dated next step, and a close date touched inside 30 days
- [ ] Weighted pipeline recounted after merges and drops

## Adapting this to your company

Swap: the per-stage day limits, the 7-day stale bar, the 30-day close-date
rule. Keep: the four-check order, time-in-stage as the stall definition,
same-day collision pauses, and the weekly ID reconciliation.
