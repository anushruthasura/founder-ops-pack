---
name: case-study-extractor
description: >
  Turn call transcripts and customer threads into a case study with
  verbatim quotes, quantified outcomes, and account-weighted evidence.
  Use when the user asks to write a case study, extract a customer story,
  or mine calls for proof points. Quotes are never invented, tightened,
  or attributed beyond what the source shows.
license: MIT
metadata:
  version: "1.0"
  tier: M
  provenance: sanitized from the customer-voice synthesis practice of a venture-backed software company
---

# Case Study Extractor

The case study is assembled from evidence, not written and then
decorated with quotes. If the evidence table is thin, the fix is another
interview, never a better adjective.

## The quote-integrity rule (hard, no exceptions)

- Quotes are verbatim from a transcript or written thread. Ellipses may
  cut, brackets may clarify a referent, nothing may be added or reworded.
- Every quote carries a source pointer: which call or thread, what date.
- Speakers are attributed at the precision the source supports: name and
  title only if stated, otherwise role. A quote is never upgraded to a
  more senior mouth.
- Paraphrase is allowed in body prose, and it is never inside quote marks.

## Build order

1. **Evidence table first.** One row per claim: the claim, the verbatim
   supporting quote, source pointer, and a number if one exists.
2. **Weight by account, not by call.** Five calls with one account is one
   account's story. Loud accounts do not get five votes.
3. **Separate felt pain from funded pain.** The pain the customer
   mentions most is often not the pain that had budget. The case study
   leads with the funded pain; the felt pain is color.
4. **Draft from the table.** Structure: before-state, the funded pain
   with its cost, the change, quantified outcomes, one honest limitation.

## If/then rules

- If a claim has no supporting quote or number → it moves to body prose
  as the author's observation, or gets cut. Claims do not borrow the
  customer's voice.
- If the outcome number came from the customer's mouth → quote it with
  its qualifier ("about 30%"). If it came from your own analytics →
  state it as yours. The two are never blended into one figure.
- If the customer asks to soften a quote → the quote changes to their new
  words or is removed. There is no third option where you edit it.
- If two sources conflict on a number → use the more conservative one and
  note the range in the evidence table.

## Worked example (real math)

Three calls across 2 accounts, plus one email thread. The evidence table
gets 11 rows. Account A (2 calls) mentions onboarding friction 9 times;
account B mentions reporting workload twice, but B's champion says, on
the record: "we budgeted two analyst hires we didn't make, that's roughly
$180,000". Felt pain: onboarding. Funded pain: reporting workload. The
draft leads with the $180,000 avoided cost, quoted verbatim with its
"roughly" intact, sourced to B's March 12 call. A's onboarding quotes
become supporting color, weighted as one account despite 9 mentions. The
customer later tightens their quote in review, and accepting it means
updating ALL affected fields together: the quote text in the draft, the
evidence-table row, and the pull-quote graphic copy. A quote fixed in
the draft but not the pull-quote ships the unapproved version anyway.

## Escalation

Every case study gets customer sign-off on their quotes and numbers
before publication, requested as a specific list ("these 4 quotes, these
2 figures"), not a whole-draft approval. No sign-off, no publication:
downgrade to an anonymized proof point.

## Validation (definition of done)

- [ ] Every quote verbatim, source-pointed, and attributed at source precision
- [ ] Evidence table complete before drafting began
- [ ] Claims weighted by account; no account speaks louder than once
- [ ] Funded pain leads; customer numbers and internal numbers never blended
- [ ] Customer signed off on the specific quote-and-number list
- [ ] One honest limitation included

## Adapting this to your company

Swap: the draft structure, the sign-off workflow. Keep: verbatim quotes
with pointers, account weighting, the felt-vs-funded distinction, and
evidence before prose.
