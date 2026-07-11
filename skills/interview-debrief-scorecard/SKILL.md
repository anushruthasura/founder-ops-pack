---
name: interview-debrief-scorecard
description: >
  Run interview debriefs on a conservative evidence-based scorecard:
  per-dimension 0-10 scores backed by confirmed evidence, written before
  discussion, decided against a preset bar. Use when the user asks to
  structure interview feedback, run a debrief, or fix hiring decisions
  made on vibes.
license: MIT
metadata:
  version: "1.0"
  tier: M
  provenance: sanitized from the conservative account-grading practice of a venture-backed software company
---

# Interview Debrief Scorecard

Score what the candidate demonstrated, not what they made you feel. The
grading rule is conservative: confirmed evidence or the points do not
exist.

## The scorecard

Built at role-definition time, not after the interviews: 5-8 dimensions,
each scored 0-10, each assigned to a named interviewer who owns probing
it. The hire bar is preset (dimension minimums plus a total floor)
before the first phone screen. Moving the bar after meeting a likable
candidate is how teams hire likable mistakes.

## The conservative grading scale

- **0-3:** no evidence, or contradicting evidence.
- **4-6:** claimed it, described it plausibly, but no verifiable specifics.
- **7-8:** confirmed evidence: a walked-through artifact, a reproduced
  result, a specific story with checkable details.
- **9-10:** confirmed evidence plus depth under follow-up pressure.

The rule that makes it work: a confident claim without specifics scores
4-6, never higher. Charisma is a 4-6 phenomenon.

## Debrief mechanics

- Scores and evidence written INDEPENDENTLY, before any discussion or
  channel chatter. First spoken opinion anchors the room otherwise.
- Every score above 6 must cite its evidence in one written line.
- The debrief compares written scores, then discusses only dimensions
  with a spread of 3+ points.
- The decision is scores against the preset bar. "I'd work with them"
  is not a dimension.

## If/then rules

- If two interviewers score the same dimension 3+ apart → each reads
  their evidence line aloud; usually one saw confirmed evidence and one
  saw claims. Re-score after, changes logged with a reason.
- If a dimension nobody probed scores above 4 → it reverts to "not
  assessed" and, if it carries a minimum, triggers a targeted follow-up
  call rather than a guess.
- If the candidate misses one dimension minimum but clears the total →
  no hire. The minimums exist for the dimensions that cannot be coached.
- If references contradict a 7+ score → the score drops to the evidence,
  and the debrief reopens if that breaks the bar.

## Worked example (real math)

Backend-lead loop, 6 dimensions, bar: no dimension under 5, total 38/60.
Four interviewers submit written scores. Systems-design spread: 8 and 5.
The 8 cites a walked-through migration design with failure modes; the 5
heard the same story without probing detail. Evidence read-out upholds
the 8 (confirmed, checkable), the 5 re-scores to 7 with a logged reason.
Final: 7, 7, 8, 5, 6, 7 = 40/60, above 38, all minimums cleared, hire.
A week later a reference reveals the "led the migration" claim was a
shared credit: the systems-design 8 drops to 6, and updating it means
updating ALL affected fields together: the dimension score, the total
(40 → 38, exactly at the bar), the evidence line noting the reference,
and the decision log showing hire-at-bar. A score quietly edited without
the total recomputed leaves the packet asserting two different decisions.

## Escalation

Bar disputes go to the hiring manager before the loop starts, never
mid-debrief. A debrief that wants to hire below the bar escalates to
whoever set the bar, in writing, with the evidence lines attached.

## Validation (definition of done)

- [ ] Scorecard and bar existed before the first interview
- [ ] All scores written independently before discussion
- [ ] Every 7+ score cites confirmed evidence in writing
- [ ] All 3+ spreads resolved by evidence read-out, changes logged
- [ ] Decision is scores-vs-bar; overrides recorded with who and why
- [ ] Post-reference score changes recompute the total and reopen if needed

## Adapting this to your company

Swap: dimension count, the bar numbers, the 3-point spread trigger.
Keep: conservative confirmed-evidence grading, independent writing
before discussion, preset bars, and evidence lines for every high score.
