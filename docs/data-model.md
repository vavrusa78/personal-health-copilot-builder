# Data model

## Design rules

- Use explicit event types.
- Normalize units.
- Preserve source metadata.
- Separate measured, reported, and inferred fields.
- Include timestamps and stable ids.

## Core entities

- meal_event
- drink_event
- biometric_measurement
- sleep_session
- activity_event
- symptom_event
- medication_event
- daily_note

## Default recommendation

Start with JSONL-friendly append flows and graduate to SQLite only when query complexity justifies it.
