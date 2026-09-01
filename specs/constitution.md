# Constitution — Habit Tracker

Non-negotiable, project-wide constraints. These apply across every feature and
every epic — if a spec ever seems to contradict this file, this file wins until
it's deliberately amended.

## Data & Time

- All timestamps are stored in **UTC** in the database.
- "Day boundary" for streak/habit-completion logic is evaluated in the **user's
  stored timezone**, never server time or UTC midnight.
- Daylight saving transitions must not silently break a streak — write a test
  for the spring-forward and fall-back transition dates.

## Tech Stack *(fill in for your team)*

- Backend: _e.g., Node.js / NestJS or Python / FastAPI_
- Frontend: _e.g., React_
- Database: _e.g., PostgreSQL or SQLite for the Capstone scope_
- Testing: _e.g., Jest / Pytest_

## Conventions

- Every business rule (anything beyond basic CRUD) requires a unit test before
  the feature is considered done.
- No AI-generated code merges without a human review pass against the spec's
  stated intent (see Phase 4 pair-programming checklist).
- Money/quantity-style fields (streak counts, reminder intervals) use integers,
  not floats.

## Security

- No user data (habit logs) is exposed via an API endpoint without an auth check.
- Any AI-generated output rendered back to a user (e.g., a summary message) is
  treated as untrusted output and sanitized before display — see the OWASP
  GenAI LLM Top 10 module from Phase 4.
