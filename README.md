# Founder Ops Pack

**Skills and agents for founders and operators — every item the sanitized
version of a real production system, or explicitly seeded from one.**

There are plenty of skill packs out there with hundreds of entries. Most are
generated in bulk, and read like it. This pack takes the opposite bet: fewer
items, and every one of them comes from a system in daily production use at a
venture-backed software company — the actual close runbook, the actual task
reconciler, the actual outbound engine — sanitized for general use. That is
the build rule for this repo: **nothing here was generated from scratch.**
Skills carry the specific numbers, thresholds, and escalation rules of the
originals; the parameters are visibly swappable, the discipline is not.

Works in Claude Code, Codex, Cursor, Gemini CLI, GitHub Copilot, and any
Agent-Skills-compatible tool. ChatGPT users: see `chatgpt/` for a paste-ready
text twin of every skill. Install instructions: [INSTALL.md](INSTALL.md).

> **Status:** the pack lands in waves through launch week — flagships first.
> Everything in the index below ships; if a skill isn't in `skills/` yet,
> it's days away. Watch the repo.

## What this replaces

Teams pay real money for the work these skills encode. Aggregate across
categories, a lean team runs into six or seven figures a year:

| You currently pay for | Typical cost | Skills / agents in this pack |
|---|---|---|
| SDR / outbound rep | $85K-$120K/yr fully loaded | `cold-email-sequencer`, `outbound-reply-triage`, agent: `outbound-sdr` |
| Customer success headcount / tooling | $70K-$120K/yr per CSM | `engagement-health-classifier`, `lifecycle-email-orchestrator`, agent: `customer-success-manager` |
| Bookkeeper / controller / fractional CFO | $3K-$22K/mo | `monthly-close-runbook`, `runway-scenario-model`, agent: `fractional-cfo-lite` |
| Executive assistant / chief of staff | $65K-$125K/yr (or $3K-$7.5K/mo fractional) | `todo-reconciler`, `meeting-prep-brief`, agents: `chief-of-staff`, `executive-assistant` |
| RevOps / sales ops analyst | $26K-$83K/yr interpretation labor | `deal-memory`, `call-to-memory`, `account-page-maintainer`, `weekly-metrics-digest`, agent: `revops-analyst` |
| Competitive intel platform + analyst | $15K-$60K/yr + labor | `voice-of-customer-synthesizer` |
| Unmanaged SaaS renewals / seat waste | typically 10-30% of SaaS spend recoverable | `vendor-stack-audit` |
| Sales engineering questionnaire time | days per enterprise deal | `rfp-security-questionnaire` |
| Launch / program management | agency retainers | `launch-command-center`, `channel-signal-digest` |

No line above is claimed lightly: every skill in this pack is the sanitized
version of a system in daily production use, or explicitly seeded from one.

## The full index

Tiers: **L** = flagship (120-180 lines, ships templates in `assets/` where
natural), **M** = standard (80-120 lines, full quality bar), **S** = utility
(40-70 lines, one sharp pattern — small but never thin).

### Skills

| Skill | What it replaces / encodes | Who it's for | Tier |
|---|---|---|---|
| `todo-reconciler` | The chief-of-staff-grade task list that stays true to reality | Everyone | L |
| `meeting-prep-brief` | Pre-meeting research an EA or chief of staff does | Everyone | L |
| `channel-signal-digest` | Reading every channel so you don't have to | Everyone | L |
| `deal-memory` | Deal-state tracking a RevOps analyst maintains | Sales / GTM | L |
| `call-to-memory` | Post-call notes that land in durable account memory | Sales / GTM, CS | L |
| `account-page-maintainer` | Account-plan upkeep with graded qualification audits | Sales / GTM | L |
| `cold-email-sequencer` | Outbound sequence writing | Sales / GTM | L |
| `outbound-reply-triage` | SDR management of the reply inbox | Sales / GTM | L |
| `lifecycle-email-orchestrator` | Lifecycle/onboarding email operations (the send-ledger rule) | Founder, CS, growth | L |
| `engagement-health-classifier` | CSM book-of-business health review | Customer success | L |
| `monthly-close-runbook` | Bookkeeper / controller month-end close | Finance | L |
| `weekly-metrics-digest` | Analyst weekly reporting | Founder, RevOps | L |
| `voice-of-customer-synthesizer` | Customer/competitive intel synthesis | Product, GTM | L |
| `launch-command-center` | Launch program management | Anyone launching | L |
| `rfp-security-questionnaire` | Security-questionnaire fire drills | Sales engineering | L |
| `metric-dictionary` | The single source of truth for what your numbers mean | Everyone | M |
| `decision-memo` | Structured decisions: options, reversibility class, decide-by date | Founder, exec | M |
| `sop-runbook-writer` | Process documentation that stays alive (last-verified dates) | Ops | M |
| `investor-update-writer` | Investor-update ghostwriting (consistent MoM table, lowlights first) | Founder | M |
| `board-meeting-pack` | Board prep: 72h pre-read rule, narrative-first, decision log | Founder | M |
| `fundraise-pipeline` | Fundraise CRM discipline: stages, pass-reason taxonomy, parallel-not-serial | Founder | M |
| `okr-quarterly-planning` | Quarterly planning: KR quality bar, 3-objective cap | Founder, exec | M |
| `runway-scenario-model` | Fractional-CFO scenario planning: base/bear/bull, triggers pre-committed | Founder, finance | M |
| `interview-debrief-scorecard` | Structured debriefs: confirmed evidence vs vibes, independent scoring | Hiring managers | M |
| `prd-one-pager` | Problem-first specs with mandatory non-goals | Product | M |
| `vendor-stack-audit` | SaaS renewal calendar, 90/60/30 negotiation windows, seat utilization | Ops, finance | M |
| `case-study-extractor` | Transcript-to-case-study drafting with a quote-integrity rule | Marketing, GTM | M |
| `delegation-brief` | Handoffs (to humans or AI agents) that don't boomerang | Everyone | S |
| `inbox-triage` | 4-decision inbox discipline + a waiting-on ledger | Everyone | S |
| `crisp-status-update` | Status updates people actually read: headline first, asks before context | Everyone | S |
| `weekly-review-reset` | The weekly review, timed so you trust the output | Everyone | S |
| `feedback-sbi` | Situation-Behavior-Impact feedback | Managers | S |
| `1on1-operating-system` | 1:1s with memory | Managers | S |
| `new-hire-30-60-90` | Onboarding plans with checkable milestones | Managers | S |
| `bug-sev-triage` | Severity x frequency matrix with an SLA per severity | Product / eng | S |
| `contract-first-pass` | Contract read-through checklist — prep for counsel, not legal advice | Founder, ops | S |
| `crm-hygiene` | Required fields and stage-exit criteria | Sales / GTM | S |

### Agents

| Agent | What it orchestrates | Who it's for |
|---|---|---|
| `chief-of-staff` | Your day: reconcile the list, prep the meetings, digest the channels | Founder, exec |
| `executive-assistant` | Calendar, follow-ups, logistics, inbox triage | Everyone |
| `meeting-copilot` | The full meeting loop: prep, notes, follow-ups, memory | Everyone |
| `outbound-sdr` | Sequences, reply triage, CRM hygiene end-to-end | Sales / GTM |
| `customer-success-manager` | Health classification and the outreach loop it drives | Customer success |
| `deal-memory-keeper` | Every call and email lands in deal memory | Sales / GTM |
| `revops-analyst` | Deal memory, account pages, pipeline and CRM hygiene | Sales / GTM |
| `fractional-cfo-lite` | Close, scenario models, metrics digests | Founder, finance |
| `metric-librarian` | Owns the metric dictionary, arbitrates every number dispute | Everyone |
| `board-prep-partner` | Board pack assembly and the running decision log | Founder |
| `product-ops-analyst` | Bug triage, spec hygiene, ship-week operations | Product / eng |
| `people-ops-partner` | Debriefs, feedback, 1:1s, 30-60-90s | Managers |

## Start here, by role

- **Founder** → `todo-reconciler`, `decision-memo`, `metric-dictionary`,
  `investor-update-writer`, `runway-scenario-model`.
- **Team of one (founder, consultant, chief of staff)** → `todo-reconciler`
  (start here, it changes your day), `meeting-prep-brief`, `inbox-triage`,
  `channel-signal-digest`, `lifecycle-email-orchestrator`.
- **Sales / GTM** → `deal-memory` + `call-to-memory`, then
  `cold-email-sequencer` + `outbound-reply-triage`, kept honest by
  `crm-hygiene`. Agent: `outbound-sdr`.
- **Finance** → `monthly-close-runbook`, `runway-scenario-model`,
  `vendor-stack-audit`. Agent: `fractional-cfo-lite`.
- **Customer success** → `engagement-health-classifier` +
  `lifecycle-email-orchestrator` (mind the send-ledger rule — it's the
  single most valuable idea in the pack), `case-study-extractor`.
- **Product / ops** → `prd-one-pager`, `bug-sev-triage`,
  `sop-runbook-writer`. Agent: `product-ops-analyst`.
- **People** → `interview-debrief-scorecard`, `feedback-sbi`,
  `1on1-operating-system`, `new-hire-30-60-90`. Agent: `people-ops-partner`.

## Quality bar

Every skill in this pack has: specific numbers and thresholds, an if/then
decision framework, escalation logic, one worked example with real math, and
a validation section (definition of done). Utility skills are small but
sharp — one pattern, still with a number, a rule, an example, and a
validation step. If anything ever reads like generic AI advice, file an
issue — that's a bug.
