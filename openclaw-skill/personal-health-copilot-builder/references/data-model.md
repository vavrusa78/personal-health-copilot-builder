# Data model

## Design rules

- Use explicit event types.
- Normalize units.
- Preserve source metadata.
- Separate measured, reported, and inferred fields.
- Include timestamps and stable ids.

## Core entities

### meal_event
- id
- timestamp
- foods[]
- kcal_estimate
- protein_g
- carbs_g
- fat_g
- source
- confidence
- notes

### drink_event
- id
- timestamp
- item
- volume_ml
- kcal_estimate
- source
- notes

### biometric_measurement
- id
- timestamp
- metric
- value
- unit
- source
- device
- confidence

### sleep_session
- id
- start_at
- end_at
- total_sleep_minutes
- efficiency_pct
- deep_minutes
- rem_minutes
- source

### activity_event
- id
- timestamp
- type
- duration_minutes
- distance_m
- calories_burned
- source

### symptom_event
- id
- timestamp
- symptom
- severity
- body_area
- source
- notes

### medication_event
- id
- timestamp
- name
- dose
- unit
- source
- notes

### daily_note
- id
- date
- text
- tags[]
- source

## Derived outputs should not replace source events

Examples:
- daily totals
- baseline comparisons
- weekly trends
- readiness-like summaries
