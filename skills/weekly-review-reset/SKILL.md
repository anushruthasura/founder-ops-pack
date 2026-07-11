---
name: weekly-review-reset
description: >
  Run the weekly reconcile: re-read the sources, auto-close what resolved
  elsewhere, and force a keep/dismiss/done call on stale items. Use when
  the user asks for a weekly review, a GTD-style reset, or says their task
  list is stale or untrustworthy.
license: MIT
metadata:
  version: "1.0"
  tier: S
  provenance: sanitized from the task reconcile engine of a venture-backed software company
---

# Weekly Review Reset

Reconcile beats append. Most tasks resolve out-of-band, in a thread, a
call, or someone else's commit. A list that only grows is a list you
will eventually stop believing.

## The reconcile pass

Weekly, timed so the list is trustworthy at week start (Sunday evening or
before 8am Monday). In order:

1. **Re-read the sources, not the list:** email, chat channels, meeting
   notes, the ticket tracker. 20-minute cap.
2. **Auto-close:** anything the sources show as resolved gets closed with
   a one-word source note. Expect 20-40% of open items to close here.
3. **Surface:** new commitments found in sources get added with a date.
4. **Stale triage:** every item untouched for 14+ days gets a forced call:
   keep (with a new date), dismiss (with one line why), or done.

## If/then rules

- If auto-close finds under 10% → you are re-reading the list instead of
  the sources. Restart from the sources.
- If an item survives 2 stale triages → dismiss it. Twice-stale means
  reality already dismissed it, the list just has not caught up.
- If the pass exceeds 45 minutes → the list is carrying projects, not
  tasks. Split anything without a single next action.

## Worked example (real math)

Sunday pass, 41 open items. Source re-read closes 12 (29%, inside the
20-40% band): 5 resolved in chat threads, 4 shipped in the tracker, 3
overtaken by a decision in Thursday's notes. That decision kills the
"draft options doc" item, and closing it means updating ALL affected
fields together: the item's status, the linked calendar hold for Tuesday,
and the owner's expectation via a one-line note. 6 items hit the 14-day
stale bar: 3 kept with new dates, 2 dismissed with reasons, 1 marked
done. Monday opens with 26 items, every one dated and believed.

## Validation (definition of done)

- [ ] Pass ran from the sources, finished inside 45 minutes
- [ ] Auto-close rate landed in or above the 10% floor, with source notes
- [ ] Zero items older than 14 days without a keep/dismiss/done call
- [ ] Closed items had their linked holds and owners updated together
- [ ] The list is dated and current before the week starts

## Adapting this to your company

Swap: the 14-day stale bar, the 45-minute cap, the pass timing. Keep:
reconcile from sources, forced stale triage, and the week-start trust rule.
