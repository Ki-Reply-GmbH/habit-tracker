# Open Questions — Habit CRUD

## Habit Deletion vs. Archiving
**Status:** RESOLVED
**Question:** Should habits be hard-deletable, or archive-only?
**Resolution:** Archive-only. Hard delete would break streak history and any
future "reactivate a habit" feature. See `specs/decisions/` if this needs to
become a formal ADR later.

## Weekday-Specific Frequency Edge Case
**Status:** OPEN
**Question:** If a habit is "Mon/Wed/Fri only," does a Tuesday check-in get
rejected, silently ignored, or recorded as an off-schedule bonus check-in?
**Owner:** whoever picks up `001-habit-crud` — resolve before writing the
check-in API, since it affects the data model.
