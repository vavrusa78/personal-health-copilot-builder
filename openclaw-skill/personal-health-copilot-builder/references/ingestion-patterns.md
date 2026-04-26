# Ingestion patterns

## Required v1 ingestion paths

### Manual text logging
Use for meals, drinks, symptoms, notes, and quick measurements.

Pattern:
1. parse user input
2. record explicit assumptions
3. write canonical event
4. recompute derived state
5. regenerate relevant report

### Generic JSON import
Use when the user already has exported data.

Pattern:
1. preserve raw payload
2. map fields into canonical schema
3. record mapping assumptions
4. validate units and timestamps

### Generic CSV import
Use for trackers, spreadsheets, and legacy exports.

Pattern:
1. inspect columns
2. define mapping
3. normalize rows
4. reject ambiguous rows explicitly

## Optional adapters

Treat these as plugins on top of the canonical system:
- wearable imports
- health platform imports
- webhook connectors
- photo-assisted food entry

## Important rule

Do not let a specific connector define the entire system schema.
