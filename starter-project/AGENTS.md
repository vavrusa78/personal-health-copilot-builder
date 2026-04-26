# AGENTS.md

This project is a portable personal health copilot workspace.

## Purpose

Use this workspace to track food, hydration, biometrics, sleep, symptoms, and daily summaries without vendor lock-in.

## Operating rules

- Treat structured data as source of truth.
- Do not keep totals only in chat history.
- Keep raw imports separate from canonical normalized data.
- Generate reports from deterministic scripts.
- Distinguish measured data, user-reported data, imported data, and inferred interpretation.
- Use conservative health language. Do not diagnose.

## Default workflow

1. Ingest or log new events.
2. Normalize them into canonical storage.
3. Recompute derived daily state.
4. Regenerate affected reports.
5. Respond with the result and uncertainty if relevant.
