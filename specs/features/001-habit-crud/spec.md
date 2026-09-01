# Spec — Habit CRUD

## Why

Users need a way to define the habits they're tracking and log daily check-ins
before any streak logic can exist.

## Requirements

- A user can create a habit with a name and a frequency (daily or specific
  weekdays).
- A user can edit or archive a habit. Archiving hides it from the active list
  without deleting history.
- A user can log a check-in for a habit for a given day (default: today).
- A user can view their habits with today's check-in status.

## Acceptance Criteria

- [ ] Creating a habit with an empty name is rejected with a clear error.
- [ ] Archiving a habit does not delete its historical check-ins.
- [ ] A duplicate check-in for the same habit + day updates, not duplicates,
      the existing entry.
- [ ] The habit list view loads in under 200ms for up to 50 habits (informal
      target, not a hard SLA for the Capstone).
