# Business Requirements — Habit Tracker
### Stakeholder brief · 3-week delivery window

**From:** Product Stakeholder (simulated client)
**To:** Engineering Team
**Re:** New habit-tracking app — MVP in 3 weeks

---

## Background

We want a simple app that helps our users build daily habits and stick to them.
Competitors' apps are cluttered — we want something focused: define a habit,
check it off, see your streak. If people feel good about their progress, they
keep using the app. That's the whole bet.

We have **3 weeks** before this needs to be in front of a small pilot group of
users. It doesn't need to be feature-complete — it needs to nail the core loop.

---

## Business Goals

1. Get a working habit-tracking loop in front of pilot users within 3 weeks.
2. Make the "streak" feel motivating, not punishing — one bad day shouldn't
   feel like starting over from zero.
3. Keep scope tight enough that what ships in 3 weeks is actually reliable,
   not a rushed feature list that's half-broken.

---

## Functional Requirements

### Must Have (Week 1–2)

| # | Requirement | Notes |
|---|---|---|
| FR-1 | Users can create a habit with a name and how often they want to do it. | "How often" — daily, or specific days of the week. |
| FR-2 | Users can check off a habit for today. | |
| FR-3 | Users can see a list of their habits with today's status at a glance. | |
| FR-4 | Users can edit or stop tracking a habit without losing their history. | We don't want "delete" — people should be able to come back to an old habit later and see their old progress. |
| FR-5 | The app tracks a "streak" — how many days in a row a habit's been completed. | This is the feature that matters most to us. See Open Questions — we know we haven't fully thought through the edge cases. |
| FR-6 | Missing **one** day shouldn't fully wipe out a streak. | We want this to feel forgiving, not punishing. We're calling this a "grace day" internally but haven't nailed down the exact rule — see Open Questions. |

### Should Have (Week 2–3, if time allows)

| # | Requirement | Notes |
|---|---|---|
| FR-7 | A reminder/notification if a user hasn't checked in by a certain time of day. | Nice-to-have for the pilot — don't let this block the Must Haves. |
| FR-8 | A weekly summary showing what got done and current streaks. | Could be an email, could be in-app — open to engineering's recommendation. |

### Won't Have (this round)

- Social features (sharing streaks, friends, leaderboards) — explicitly out of
  scope for the pilot. We want to validate the core loop first.
- Multiple habit categories or tagging — too much scope for 3 weeks.
- Native mobile app — web is fine for the pilot.

---

## Non-Functional Requirements

- **Reliability over polish.** A pilot user losing their streak data because
  of a bug is a worse outcome than the UI looking a little rough.
- **Works correctly for users in different timezones.** We have pilot users
  on both US coasts and in Europe — a habit "day" needs to mean *their* day,
  not our server's day.
- **Data isn't lost or corrupted** if a user changes their timezone (e.g.,
  travel) mid-streak. We don't have a strong opinion on the *exact* behavior
  here — just don't silently break someone's streak count.
- Response times should feel snappy for a pilot group of ~50–100 users — we
  are not asking for enterprise-scale performance work in 3 weeks.

---

## Open Questions *(intentionally left for engineering to raise, not answer here)*

The stakeholder side of this brief is deliberately underspecified in a few
places — this is realistic, and part of the exercise is surfacing these as
`open-questions.md` entries before implementation, not guessing:

1. Exact grace-day rule (FR-6): does it reset every week, every streak, or is
   it a rolling "one free pass per 7 days"? Stakeholder hasn't decided.
2. What happens to a streak if a user changes their timezone mid-streak
   (e.g., travels)? Stakeholder only knows they don't want it to "silently
   break" — no precise rule given.
3. Weekly summary delivery channel (FR-8): email vs. in-app — stakeholder is
   explicitly deferring this to engineering's judgment.
4. What "stop tracking" (FR-4) means for a habit's streak count if the user
   re-activates it later — does the old streak resume, or restart at zero?

---

## Suggested 3-Week Timeline

| Week | Focus |
|---|---|
| **Week 1** | Habit CRUD (FR-1 to FR-4) + resolve Open Questions 1, 2, and 4 before building streak logic |
| **Week 2** | Streak tracking with grace day (FR-5, FR-6) — the core feature; timezone correctness is a hard requirement, not a stretch goal |
| **Week 3** | Should Have features if time allows (FR-7, FR-8), plus hardening, testing, and pilot readiness — cut FR-7/FR-8 first if the schedule is at risk, not the Must Haves |

---

## Success Criteria for the Pilot

- A pilot user can create a habit, check in daily, and see an accurate streak
  without needing support intervention.
- No reported cases of a streak being wrong due to timezone or day-boundary
  bugs.
- The team can clearly explain, for every Must Have requirement, what was
  built and why — a spec trail, not just working code.