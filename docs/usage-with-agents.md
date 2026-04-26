# Usage with agents

## Core rule

Keep the core architecture generic. Do not let one connector, wearable, or vendor export define the whole system.

## OpenClaw

Use the packaged skill in `openclaw-skill/` when you want an OpenClaw agent to design or implement a health copilot system.

Recommended order:
1. define scope
2. define canonical model
3. define storage
4. define ingestion
5. define derived reports
6. define safety boundaries
7. implement the smallest useful v1

## Codex / Claude Code / similar

Use the repository directly:
1. read `docs/blueprint-v1.md`
2. copy `starter-project/`
3. adapt the schema and ingestion flow
4. implement deterministic calculations
5. add summaries and optional presentation layers

## Good first build

A strong first build is usually:
- meals
- hydration
- one biometric import path
- one daily summary
- one report regeneration flow

## Avoid

- vendor-first schema design
- hidden arithmetic in chat replies
- diagnostic positioning
- presentation logic before canonical storage
