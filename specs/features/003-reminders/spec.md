# Spec — Reminders / Weekly Summary

## Why

Good candidate for the Phase 4 multi-agent pipeline exercise and the Phase 5
solo end-to-end Capstone feature — it touches scheduling (a natural fit for
parallel worktree work: one agent builds the scheduler, another the summary
content) without depending on the streak-tracking internals being finalized.

## Requirements (draft — flesh out during Phase 1/3 for your cohort)

- The system SHALL send a reminder if a user has not checked in for a
  scheduled habit by a configurable time of day (in the user's timezone).
- The system SHALL send a weekly summary (habits completed, current streaks,
  grace days remaining) once per week.
- Reminder/summary content is treated as untrusted AI-generated output if
  generated dynamically — sanitize before rendering (see `constitution.md`).

## Acceptance Criteria

- [ ] To be written by whoever picks this up — use this as practice writing a
      spec from a rough idea rather than a fully worked example.
