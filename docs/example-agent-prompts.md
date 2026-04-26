# Example agent prompts

## Generic builder prompt

Build me a local-first personal health copilot using this repository as the blueprint.
I want support for food logging, hydration, basic biometrics, and daily summaries.
Keep the system vendor-agnostic, deterministic, and conservative in health language.
Start with the smallest useful v1.

## Nutrition-focused prompt

Use this repository to build a nutrition and hydration tracking workspace.
Prioritize meal logging, water intake, protein totals, and an evening recap.
Do not assume Oura, Apple Health, or any wearable integration.

## Recovery-focused prompt

Use this repository to build a recovery tracking workspace with sleep and biometrics summaries.
Keep ingestion generic so I can connect any wearable later.
Do not design around one vendor export.

## OpenClaw-oriented prompt

Use the `openclaw-skill/` package in this repository to design and implement a health copilot workspace.
Return scope, canonical model, storage layout, ingestion flows, summaries, safety boundaries, and concrete starter files.
