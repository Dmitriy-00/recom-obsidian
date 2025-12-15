# Transformative Media Recommender (Obsidian)

This repository stores the Obsidian-native knowledge base and logic for a transparent, explainable media recommender. Obsidian markdown files with YAML frontmatter are the source of truth; logic lives alongside but separate from media content. CSV exports mirror the Obsidian structure for downstream ingestion.

## Repository layout
- `00_SYSTEM/` — system-wide conventions, schema contracts, and glossary.
- `01_REGISTRIES/` — controlled vocabularies (genres, themes, tropes, cognitive operations) with no media instances.
- `02_TAXONOMIES/` — semantic relationships between registry items.
- `03_MEDIA/` — media entities (initially films) stored as Markdown with YAML frontmatter only.
- `04_USERS/` — user profiles and preference data in YAML frontmatter.
- `05_LOGIC/` — deterministic scoring and filtering logic (Dataview/DataviewJS prototypes).
- `06_VIEWS/` — Dataview/Bases definitions and explainability-facing views.
- `07_EXPORT/` — CSV schemas and generated exports for analytics or API ingestion.

## Core principles
- Obsidian is the semantic core and source of truth; media files contain data only.
- Strict separation of layers: data, registries, taxonomies, logic, views, and export artifacts.
- Explainable, deterministic scoring built as weighted linear compositions; no opaque ML in the MVP.
- CSV is the exchange format for migrations to SQL/APIs/bots.

## Getting started
1. Review `00_SYSTEM/schema.md` for the canonical YAML contracts.
2. Populate registries in `01_REGISTRIES/` before adding media or user files.
3. Use `03_MEDIA/Films/templates/film-example.md` and `04_USERS/templates/user-example.md` as guides.
4. Implement or adjust scoring weights in `05_LOGIC/scoring.md` and mirror them in exports.
