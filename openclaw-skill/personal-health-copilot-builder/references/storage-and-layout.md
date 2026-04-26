# Storage and layout

## Principles

- Keep source of truth inspectable.
- Prefer local-first storage.
- Do not bury canonical state inside agent memory.
- Generate reports from structured data.

## Good default layout

```text
health/
  raw/
  canonical/
  reports/
  config/
meals/
  logs/
  reports/
scripts/
docs/
```

## Suggested storage roles

### raw/
Vendor dumps, webhook payloads, imports.

### canonical/
Normalized JSON, JSONL, or SQLite records.

### reports/
Derived markdown and summary artifacts.

### config/
User-specific goals, units, targets, connector settings.

## Decision heuristics

Use JSONL when:
- append-heavy events dominate
- human inspectability matters
- the system is still evolving

Use SQLite when:
- joins and trend queries become heavy
- consistency matters more than raw simplicity
- event volume grows

Hybrid is often best:
- append logs for ingestion
- SQLite or normalized JSON for canonical state
- markdown for review
