# Founder Ops Pack

This repository is a collection of **agent skills** and **agent playbooks** for
founders and operators. Each skill is a self-contained folder under `skills/`
with a `SKILL.md` (YAML frontmatter + markdown body). Each agent is a markdown
playbook under `agents/`.

## How agents should use this repo

- Load a skill when the user's task matches its `description` frontmatter
  (each description states what the skill does AND when to use it, with
  trigger keywords).
- Skills are independent: loading one never requires another, though some
  reference companion skills by name (e.g. `cold-email-sequencer` pairs with
  `outbound-reply-triage`).
- Agents under `agents/` are personas that orchestrate one or more skills.
  Delegate to them for role-level work ("act as my fractional CFO"), use
  skills directly for task-level work ("run my month-end close").
- Every skill ends with a **Validation** section — a definition of done.
  Do not report a skill's task complete until its validation checks pass.
- Skills contain specific numbers and thresholds (e.g. review bands, staleness
  windows). These are opinionated defaults from real operating experience —
  keep them unless the user overrides them, and if the user overrides them,
  keep the *structure* (there must always be a threshold; the value is
  swappable, the existence of the rule is not).

## What this pack is

These are sanitized versions of real internal systems run daily at a
venture-backed software company — not generated templates. Parameters that
are company-specific (metric names, tool names, dollar thresholds) are
marked as swappable throughout. The decision frameworks are not.
