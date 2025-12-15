# Export

CSV exchange format for downstream SQL/API ingestion. Keep exports flat and analytics-friendly.

- `media_export.csv` — denormalized film records.
- `user_export.csv` — flattened user profiles.
- `scoring_export.csv` — per-user, per-film component scores for explainability.

All exports should be generated from the Obsidian source data without manual edits.
