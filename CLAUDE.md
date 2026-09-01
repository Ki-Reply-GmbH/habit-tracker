# CLAUDE.md — Habit Tracker

You are working in the Habit Tracker Capstone project for the "From Spec to Ship"
learning track. Follow these rules before writing any code.

## Before implementing anything

1. Read `specs/constitution.md` — these are non-negotiable, project-wide constraints.
2. Read the relevant `specs/features/<feature>/spec.md` for the feature you're touching.
3. Check `specs/features/<feature>/open-questions.md`. If a question relevant to your
   task is not marked `RESOLVED`, **stop and ask** — do not assume a resolution.
4. Once `openspec/` exists (Phase 3 onward), treat `openspec/specs/` as the current
   source of truth and `openspec/changes/` as work in flight. Do not hand-edit
   `openspec/specs/` directly — that's what `/opsx:archive` is for.

## While implementing

- If you hit something the spec didn't anticipate, **stop** — do not silently work
  around it. Flag it, and wait for the spec (`specs/spec.md` or the OpenSpec delta)
  to be updated before continuing.
- Every business rule (especially streak/timezone logic) needs a unit test.
- Dates are stored in UTC; "day boundary" logic for streaks uses the user's stored
  timezone, not server time — see `specs/constitution.md`.

## Tools

- GitHub MCP connector is available for reading issues/PRs. Read-only actions
  (listing, reading) are safe to run without asking. Opening a PR or commenting
  requires explicit human approval first — see `docs/tooling-decision.md`.
