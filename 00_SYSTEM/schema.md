# YAML Schemas (Canonical Contracts)

The frontmatter below defines the required and optional fields for films and users. Keep media files data-only; do not embed logic or presentation.

## Film schema
```yaml
id: string
type: film

title: string
year: integer
creators: [string]

genres: [string]
themes: [string]
tropes: [string]
core_concepts: [string]

cognitive_operations: [string]

difficulty_level: 1-10
emotional_intensity: 1-10
moral_ambiguity: 0-1
accessibility: 1-10

transformative_score: 0-10

transformative_elements:
  cognitive_dissonance: boolean
  perspective_shift: boolean
  reflection_trigger: boolean
  identity_challenge: boolean

trigger_warnings: [string]

annotation_confidence: 1-10
annotation_status: draft | validated | reviewed
```

## User schema
```yaml
user_id: string
profile_type: viewer | analyst | walker

experience_level: 0-1

genre_literacy:
  <genre>: 0-1

trope_preferences:
  likes: [string]
  dislikes: [string]

trope_fatigue:
  <trope>: low | medium | high

emotional_state: string

cognitive_goals:
  reflection: boolean
  challenge: low | medium | high
  comfort: boolean
```

## Conventions
- All values must be deterministic and manually auditable.
- Registries under `01_REGISTRIES/` define allowed values for genres, themes, tropes, and cognitive operations.
- No media instance should introduce values outside registries without a prior registry update.
