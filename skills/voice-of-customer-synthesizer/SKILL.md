---
name: voice-of-customer-synthesizer
description: Synthesize calls, tickets, and threads into account-weighted pattern pages correlated with won/lost outcomes - built on the rule that the most-FELT pain is not the most-FUNDED pain. Use quarterly or before any roadmap/positioning decision.
---

# Voice of Customer Synthesizer

Customer and competitive intelligence synthesis, sanitized from a production
system that mines call transcripts into pattern pages. Its two rules exist
because the naive version of this job produces confident, wrong conclusions.

## Rule 1: account-weighted, never call-weighted

Count patterns by ACCOUNT, not by mention. One frustrated champion at one
account can generate 15 mentions of an issue across calls; 15 mentions from
one account is ONE data point. Call-weighted synthesis systematically
over-weights your chattiest accounts - which are usually your healthiest
ones, precisely the accounts whose pains you already know. Every pattern
page reports: N accounts (the number that matters), M mentions (color).

## Rule 2: most-FELT pain is not most-FUNDED pain

The pain customers talk about most is not the pain they'll pay to solve.
Felt pain is loud, daily, and workaround-able; funded pain is what appears
in their goals, budgets, and buying criteria. So every pattern is correlated
with OUTCOMES: does this pattern appear more in won deals or lost ones?
In expansions or churns? A pain that dominates transcripts but shows zero
correlation with outcomes is a UX backlog item; a quiet pain that appears
in 4 of 5 lost deals is your roadmap.

## The 5 pattern pages

Synthesis output is exactly five pages (cap forces prioritization):

1. **Top pains** - account-weighted, each with outcome correlation.
2. **Competitive dynamics** - who appears, in what context, with what result.
3. **Winning language** - the customer's own words in won deals: what they
   say the product IS. (This page writes your positioning for you.)
4. **Losing patterns** - what was present in lost/churned accounts: objections
   never overcome, stakeholders never reached, timing signals missed.
5. **Emerging signals** - new this period: too few accounts to weight, worth
   watching. Each entry expires next period unless it recurs (no zombie signals).

Every claim on every page: verbatim quote + account (anonymized if shared
externally) + date + outcome. Paraphrases drift toward what the writer
already believed; quotes don't.

## If/then

- If a pattern is loud (many mentions) but thin (few accounts) -> it goes to
  Emerging at most; note WHICH account is generating volume and why.
- If a pattern appears in both won AND lost deals at similar rates -> it's
  table stakes context, not signal; one line, no more.
- If two patterns co-occur in the same accounts (the pricing objection
  always follows the missing-feature gap) -> merge into one causal
  hypothesis; co-occurring patterns treated separately produce double-counted
  urgency.
- If this period's synthesis contradicts last period's -> BOTH go in front of
  the reader with the delta explained. Silent reversals destroy the artifact's
  credibility; visible reversals build it (the market moved, and you saw it).

## Escalation

- A losing pattern crosses 50% of lost deals in the period -> it stops being
  research; brief the owner of that function directly with the quotes.
- A competitor's appearance rate doubles period-over-period -> flag to
  leadership now, not at the quarterly readout.

## Worked example

Quarterly run: 47 accounts touched (61 calls, 340 tickets, 12 threads).
Export delays: 31 mentions - but 24 from TWO accounts -> 6 accounts weighted;
correlation: appears in 1 of 8 lost deals, 0 churns -> felt-not-funded ->
two lines on Top Pains, backlog note. Security review friction: 9 mentions,
8 accounts, present in 5 of 8 lost deals (deals died IN review) -> funded
pain, top of page, quotes attached -> briefed to product same week (crossed
the 50% line). Winning language: 6 of 7 won deals independently said some
form of "finally, one place where..." -> handed to marketing verbatim.
Emerging: 2 accounts asked about a new compliance regime -> logged with
expiry. Last quarter's #1 pain (onboarding time) dropped to #4 with the
delta explained (the fix shipped; mentions collapsed). Five pages, 40
minutes to read, three decisions traceable to it by next quarter.

## Definition of done

- [ ] Every pattern account-weighted, N-accounts and M-mentions both shown
- [ ] Every pattern carries won/lost/churn correlation, even if "none found"
- [ ] Exactly 5 pages; emerging entries carry expiry
- [ ] Every claim has quote + account + date + outcome
- [ ] Contradictions with last period surfaced with deltas
- [ ] At least one felt-vs-funded call made explicitly (that's the analysis)

## Anti-patterns

- **Call-weighted "themes".** The loudest account sets the roadmap; the quiet
  majority churns. N-accounts is the only defensible count.
- **Synthesis without outcomes.** A pattern list with no won/lost correlation
  is a mood board. The correlation column is what makes it analysis.
- **Paraphrase drift.** Summaries written from memory converge on what the
  writer already believed. Quotes with dates and outcomes resist that pull.
- **Zombie emerging signals.** Last quarter's "worth watching" that nobody
  re-validated becomes this quarter's assumed fact. Expiry dates or it
  didn't happen.

## Setup (first run, ~1 hour + the synthesis itself)

1. Inventory your language sources: call transcripts, tickets, community
   threads, sales notes. Note coverage gaps (e.g., "no transcripts before
   March") on the output.
2. Build the account spine first: every source item tagged to an account,
   every account tagged with outcomes (won/lost/churned/expanded/active).
   The spine is 80% of the work and 100% of the credibility.
3. Extract candidate patterns per account (not per call), then weight.
4. Correlate each pattern against outcomes; write the felt-vs-funded call
   explicitly for at least the top 3 pains.
5. Draft the 5 pages; every claim gets quote + account + date + outcome
   before it ships. If a claim can't find its quote, it isn't a finding.

## Swappable parameters

- Cadence: quarterly -> monthly above ~100 active accounts
- Sources: calls/tickets/threads -> whatever holds customer language
- Escalation lines: `50%` of losses, `2x` competitor rate -> your risk bar
- Page cap: `5` -> defend it before raising it
