# Spec — Streak Tracking with Grace Day

## Why

Streaks are the core motivational feature. Getting the edge cases wrong (timezones,
DST, what a "grace day" actually forgives) is the single easiest way to erode user
trust in the product — this is deliberately the feature used for the Phase 3
OpenSpec `propose → apply → archive` exercise.

## Requirements

- The system SHALL calculate a user's current streak as the number of
  consecutive scheduled days with a completed check-in, evaluated in the
  user's stored timezone.
- The system SHALL allow exactly one "grace day" per streak: one missed
  scheduled day does not reset the streak, but a second consecutive miss does.
- The system SHALL NOT let a grace day be used twice in a row to cover two
  consecutive misses.
- The system SHALL correctly evaluate day boundaries across a daylight saving
  transition without incorrectly resetting or extending a streak.

## Scenarios

#### Scenario: Grace day forgives one miss
- GIVEN a user with a 5-day streak and no grace day used yet
- WHEN they miss one scheduled day and then check in the next scheduled day
- THEN the streak continues at 6, and the grace day is marked used

#### Scenario: Two consecutive misses reset the streak
- GIVEN a user who has already used their grace day on this streak
- WHEN they miss another scheduled day
- THEN the streak resets to 0

#### Scenario: DST transition does not corrupt streak
- GIVEN a user in a timezone observing daylight saving
- WHEN the check-in day crosses a DST transition (spring-forward or fall-back)
- THEN the streak calculation still counts exactly one calendar day, not zero
  or two

> This spec is intentionally left slightly incomplete — the timezone-change and
> leap-day cases are **not** specified here on purpose. They're the deviation
> you're expected to catch mid-`/opsx:apply` during the Phase 3 checkpoint.
