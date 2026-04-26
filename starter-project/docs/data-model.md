# Data model

## Canonical entities

- meal_event
- drink_event
- biometric_measurement
- sleep_session
- activity_event
- symptom_event
- medication_event
- daily_note

## Rules

- Every record gets a stable id.
- Every record carries a timestamp or date.
- Units must be normalized.
- Source metadata must be preserved.
- Inference should be stored separately from measured or reported data.

## Initial storage choice

Use JSONL for append-heavy logs and simple local inspection.
Add SQLite later if queries become heavy.
