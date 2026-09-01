# ADR 0001 — Timezone Handling Strategy

**Status:** Proposed

## Context

Streak logic (see `specs/features/002-streak-tracking/`) depends heavily on
correct day-boundary evaluation across timezones and DST transitions. This is
a cross-cutting decision, not scoped to one feature, so it belongs here rather
than buried in one feature's `open-questions.md`.

## Decision

_Fill in once resolved — e.g., "store the user's IANA timezone string
(`Europe/Berlin`, not a raw UTC offset) and use `<library>` for all day-boundary
math."_

## Consequences

_What does this make easy? What does it make harder? What has to change if a
user travels across timezones mid-streak (see the linked open question)?_

## Related

- `specs/features/002-streak-tracking/spec.md`
- `specs/features/002-streak-tracking/open-questions.md`
