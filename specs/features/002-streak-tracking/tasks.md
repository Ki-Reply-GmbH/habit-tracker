# Tasks — Streak Tracking with Grace Day

- [ ] Extend `habit` model with `grace_day_used_at` per streak cycle
- [ ] Streak calculation function: walk scheduled days backward from today,
      counting consecutive completions, applying the one-grace-day rule
- [ ] Handle DST transition in day-boundary comparison (use a timezone-aware
      date library, not raw UTC day math)
- [ ] API: expose current streak + grace-day-available flag on habit list
- [ ] Tests: all three scenarios in `spec.md`
- [ ] Tests: at least one DST spring-forward and one fall-back date
- [ ] *(added mid-apply, see open-questions.md)* handle user changing timezone
      mid-streak
