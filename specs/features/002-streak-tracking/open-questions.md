# Open Questions — Streak Tracking

## Timezone Change Mid-Streak
**Status:** OPEN — expected deviation for the Phase 3 Capstone checkpoint
**Question:** If a user changes their stored timezone mid-streak (e.g., travel),
does the streak recalculate day boundaries retroactively, or only going forward?
**Why it's here:** this is the gap the spec deliberately leaves open. When
`/opsx:apply` hits this during implementation, stop, resolve it here, update
`specs/spec.md` and `tasks.md` accordingly, then resume. Log the resolution in
your PR description per the Phase 3 checklist.

## Leap Day
**Status:** OPEN
**Question:** Does Feb 29 count as a normal scheduled day for "daily" habits,
with no special handling needed? (Probably yes — confirm and close this out
quickly so it doesn't become the deviation instead of the timezone one.)
