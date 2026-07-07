---
name: monthly-close-runbook
description: >
  Run a company's monthly financial close as a set of small, reviewable
  workpapers instead of one monolithic scramble. Use when closing the books,
  preparing month-end journal entries, reconciling payroll, computing accruals
  (bonus, PTO), amortizing prepaids, updating fixed assets or lease schedules,
  or calculating commissions. Trigger keywords: month-end close, closing the
  books, accruals, prepaids, workpaper, reconciliation, journal entries.
---

# Monthly Close Runbook

Run the close the way a good controller runs it: **one workpaper per topic,
a hard split between "prepare" and "finalize", and a calendar driven by
business days — never calendar days.**

## The three rules that make this work

### 1. One workpaper per topic — never one giant close file

Each close topic is its own self-contained workpaper with its own inputs,
its own logic, and its own output journal entry. The standard set:

| Workpaper | What it computes | Typical input |
|---|---|---|
| Prepaids | Monthly amortization of prepaid expenses | Prepaid schedule + new invoices |
| Bonus accrual | Accrued bonus expense for the month | Comp plan targets x YTD attainment |
| PTO accrual | PTO liability delta | HR balances report x loaded hourly rates |
| Fixed assets | Depreciation + additions/disposals | FA register + purchase invoices > capitalization threshold |
| Lease expense | Straight-line lease expense vs cash | Lease schedule |
| Commissions | Commission expense + payable | Closed-won report x plan rates |
| Payroll reconciliation | GL payroll vs payroll-provider reports | Payroll register vs GL detail |
| Financials update | Roll everything into the reporting model | All finalized workpapers |

Why: when the bonus accrual is wrong, you re-run ONE workpaper — not the
whole close. And a reviewer can approve topic-by-topic instead of
rubber-stamping a monolith.

Set a **capitalization threshold** (commonly $2,500–$5,000 for small
companies) and put it IN the fixed-assets workpaper header. Anything below
it expenses immediately; never decide this ad hoc per invoice.

### 2. Prep / finalize split — a human gate between compute and commit

Every workpaper runs in two explicit phases:

- **Prep**: pull inputs, compute, produce a draft workpaper with the proposed
  journal entry and a diff vs last month. NOTHING posts.
- **Finalize**: a human reviews the draft, then (and only then) the entry is
  committed to the GL.

Never merge the phases, no matter how routine the topic looks. The month
prep-and-post runs unattended is the month a payroll provider changes a
report format and garbage posts silently.

Review triage thresholds (tune to your size, but have numbers):
- Line moved **< 5% and < $1,000** vs prior month → skim the diff, finalize.
- Line moved **5–20% or $1,000–$10,000** → read the workpaper's input section
  before finalizing.
- Line moved **> 20% or > $10,000** → do not finalize until you can explain
  the movement in one written sentence on the workpaper. If you can't
  explain it after 30 minutes of digging, escalate to whoever owns the
  source system (payroll admin, sales ops) — do not "plug" it.

### 3. The close calendar runs on business days, not calendar days

"Close by the 5th" breaks every month with a weekend or holiday in the first
week. Define the calendar as business days (BD) after month end, with a
holiday calendar applied:

- **BD1**: Payroll reconciliation prep; prepaids prep.
- **BD2**: Accruals prep (bonus, PTO); fixed assets + lease prep. Finalize BD1 items.
- **BD3**: Commissions prep. Finalize BD2 items.
- **BD4**: Finalize commissions. Financials update prep.
- **BD5**: Finalize financials. Close is done.

Dependencies are explicit: financials update cannot prep until every other
workpaper is finalized. If BD3 slips, everything downstream slips — surface
that immediately rather than compressing review time.

## Worked example: PTO accrual workpaper (a real month)

Inputs: HR report says total PTO balance across 42 employees = 2,180 hours.
Loaded cost (salary + payroll tax + benefits, ~1.25x base) averages $58/hr.

- Liability this month: 2,180 x $58 = **$126,440**
- Liability last month: $121,800
- Journal entry: Dr PTO expense $4,640 / Cr PTO liability $4,640
- Diff check: +3.8% and $4,640 — under the 5%-band? No ($4,640 > $1,000),
  so read inputs: 3 new hires added balances, 1 departure paid out. Movement
  explained in one sentence → finalize.

## Validation (definition of done)

A close is done only when ALL of these pass:
1. Every workpaper's journal entry ties to the GL (re-pull GL after posting
   and diff — do not trust "it posted").
2. Payroll reconciliation delta between GL and payroll register is **$0.00**,
   or every non-zero line has a written explanation. There is no acceptable
   unexplained payroll variance, however small — small unexplained deltas
   are how systematic mapping errors hide.
3. The financials update shows month-over-month movement per line, and every
   line breaching the >20%/$10K band has its one-sentence explanation.
4. Next month's recurring items (prepaid schedule, lease schedule, FA
   register) are rolled forward NOW, not at next close.

## Adapting this to your company

Swap the workpaper list for your topics — the pattern holds for any close.
A 5-person startup might run 4 workpapers (payroll, prepaids, revenue,
financials); a 200-person company might run 15. The three rules do not
change: topic-per-workpaper, prep/finalize gate, business-day calendar.
