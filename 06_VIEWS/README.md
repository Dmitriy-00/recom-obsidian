# Views

Dataview and Bases configurations that present explainable recommendations. Keep these declarative and free of data mutations.

Suggested entries:
- `film-score-table.md` — shows per-component scores for a selected user.
- `registry-coverage.md` — highlights missing registry coverage in media files.

Ensure views read from `03_MEDIA/` and `04_USERS/` but never write back.
