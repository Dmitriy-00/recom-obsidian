# Scoring (Deterministic, Explainable)

Weighted linear composition; all components must be traceable to data available in media and user profiles.

```text
score =
  trope_match * W1 +
  theme_match * W2 +
  cognitive_match * W3 +
  emotional_fit * W4 +
  novelty * W5
  - trope_fatigue_penalty
```

## Default weights
- `W1` (trope_match): 0.25
- `W2` (theme_match): 0.20
- `W3` (cognitive_match): 0.20
- `W4` (emotional_fit): 0.20
- `W5` (novelty): 0.15

Weights should be mirrored identically in DataviewJS prototypes and any CSV/SQL or API consumer to keep outputs reproducible.

## Component outlines
- **trope_match**: overlap between film tropes and user `trope_preferences.likes`, normalized by total likes.
- **theme_match**: overlap between film `themes` and user-preferred themes (if tracked later), normalized.
- **cognitive_match**: overlap between film `cognitive_operations` and user challenge/reflection goals.
- **emotional_fit**: closeness between film `emotional_intensity` and user emotional state/desired challenge.
- **novelty**: inverse of prior recommendations or low trope fatigue; decrease score when `trope_fatigue` is medium/high.
- **trope_fatigue_penalty**: explicit deduction based on fatigue values for tropes present in the film.

Document calculations in DataviewJS to surface per-component contributions for explainability.
