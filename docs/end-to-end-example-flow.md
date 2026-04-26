# End-to-end example flow

This example shows the intended shape of a small but complete v1.

## Goal

Build a local-first personal health copilot that supports:
- meal logging
- hydration logging
- one generic biometrics input
- deterministic day totals
- one daily summary

## Step 1: Start from the starter project

Copy `starter-project/` into a fresh workspace.

This gives you:
- a place for canonical events
- a basic docs structure
- example config
- starter scripts for deterministic reporting

## Step 2: Define the first canonical events

For v1, keep the event model small:
- `meal_event`
- `drink_event`
- `biometric_measurement`
- optional `daily_note`

Use append-friendly structured files so the system stays inspectable.

## Step 3: Add the first real inputs

A strong first version usually uses:
- manual meal logging
- manual hydration logging
- one imported biometric such as HRV, weight, resting heart rate, or sleep duration

Do not start by integrating five different data sources.

## Step 4: Compute deterministic totals

Before writing summaries, calculate facts from structured data:
- kcal total
- protein total
- hydration total
- latest biometrics for the day

All arithmetic should happen in scripts or deterministic transforms, not inside chat prose.

## Step 5: Render one daily summary

Generate one markdown summary for the day.

Example shape:
- intake
- hydration
- recovery
- notes
- cautious interpretation

The summary should clearly separate:
- measured data
- user-reported data
- inferred interpretation

## Step 6: Regenerate instead of hand-editing

If source data changes, re-run the report generator.

That keeps the system auditable and avoids silent drift between source events and narrative summaries.

## Step 7: Only then add richer presentation

After the core is stable, add optional layers such as:
- cards
- dashboards
- morning recap formatting
- short video or media output

These should sit on top of canonical and derived data, not replace them.

## Minimal success criteria

A good v1 is done when it can:
- store meals and hydration in canonical form
- accept at least one biometric measurement
- compute deterministic day totals
- generate one daily summary from structured inputs
- stay vendor-agnostic and non-diagnostic

## Anti-patterns

Avoid:
- starting with one vendor export as the system design
- keeping critical totals only in markdown
- mixing raw imports with canonical normalized events
- letting the model improvise arithmetic in final summaries
- claiming health conclusions stronger than the underlying data supports
