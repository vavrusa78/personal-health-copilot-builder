---
name: personal-health-copilot-builder
description: Build a portable personal health, nutrition, hydration, biometrics, and recovery tracking system for an agent. Use when the user wants an agent to design or implement a reusable health copilot architecture with canonical storage, ingestion flows, deterministic calculations, daily or weekly summaries, safety guardrails, and optional presentation layers such as cards or video. Trigger this for requests about creating a health-tracking workspace, food and drink logging system, biometrics pipeline, recovery summaries, or a generic wellness copilot without vendor lock-in.
---

Build the system in this order:

1. Define scope.
2. Define canonical data model.
3. Define storage layout.
4. Define ingestion flows.
5. Define derived calculations and report flows.
6. Define safety boundaries.
7. Implement the smallest useful v1.

## Output contract

Return these sections unless the user asked for a different format:
- Goal
- Scope v1
- Assumptions
- Canonical data model
- Storage design
- Ingestion flows
- Derived reports
- Safety boundaries
- Implementation plan
- Files to create or change

When implementation is requested, create concrete files rather than stopping at a plan.

## Hard rules

- Start from domain objects, not from a vendor export.
- Keep raw, canonical, derived, and presentation layers separate.
- Do not use agent memory as source of truth for totals or health state.
- Do not do hidden arithmetic in narrative text; calculations must come from deterministic scripts or structured data.
- Distinguish clearly between measured data, user-reported data, imported data, and inferred interpretation.
- Keep health language conservative and non-diagnostic.
- Prefer generic adapters over source-specific assumptions.

## Build order

### 1) Define scope

Read `references/architecture.md`.

Decide:
- which domains are in v1: meals, hydration, sleep, biometrics, symptoms, activity, medications, notes
- which inputs are manual vs imported
- which summaries are required
- what is explicitly out of scope

Keep v1 narrow enough to ship.

### 2) Define canonical data model

Read `references/data-model.md`.

Create or refine canonical entities for the selected scope.

Minimum pattern:
- stable ids
- timestamps
- source metadata
- confidence/uncertainty where relevant
- normalized units
- explicit event type

### 3) Define storage design

Read `references/storage-and-layout.md`.

Choose local-first storage that is easy to inspect and hard to corrupt.

Prefer:
- append-friendly logs for user-entered events
- canonical structured storage for normalized records
- generated reports as derived artifacts, not source of truth

### 4) Define ingestion flows

Read `references/ingestion-patterns.md`.

Support at least:
- manual text logging
- generic JSON or CSV import

If the user wants vendor integrations, add them as adapters on top of the generic model.

### 5) Define summaries and derived reports

Read `references/summary-patterns.md`.

Design deterministic outputs for:
- running daily status
- morning recap
- evening recap
- optional weekly trend

If media output is requested, keep it as a presentation layer over structured summary data.

### 6) Define safety boundaries

Read `references/safety-boundaries.md`.

The system must:
- avoid diagnosis
- avoid overclaiming from sparse signals
- separate fact from interpretation
- state blockers or missing data directly

### 7) Implement the smallest useful v1

Create a working thin slice:
- one canonical storage path
- one or two ingestion paths
- one deterministic daily summary
- one clear validation or test step

## Anti-patterns

Reject or correct these patterns:
- Oura-first or Apple-Health-first schema design
- summary logic without a canonical store
- totals computed ad hoc in agent replies
- mixing personal persona work with system architecture too early
- storing private health state only in markdown memory files
- presentation layer tightly coupled to one data source

## References

- Architecture: `references/architecture.md`
- Data model: `references/data-model.md`
- Storage/layout: `references/storage-and-layout.md`
- Ingestion: `references/ingestion-patterns.md`
- Summaries: `references/summary-patterns.md`
- Safety: `references/safety-boundaries.md`
- Publishing/portability: `references/publishing-and-portability.md`

## Template assets

If you need starter scaffolding, use:
- `assets/templates/` for lightweight planning templates
- `assets/starter-project/` for a repo-friendly scaffold with starter docs, config, example events, and placeholder scripts

When the user wants something portable across OpenClaw, Codex, Claude Code, or similar agent workflows, keep the core architecture generic and isolate OpenClaw-specific packaging or conventions to a subfolder instead of baking them into the whole project.
