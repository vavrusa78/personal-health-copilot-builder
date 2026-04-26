# Personal Health Copilot Builder — v1 blueprint

## Goal

Pomoci agentovi navrhnout a postavit přenositelný osobní health / nutrition / recovery systém bez vendor lock-inu.

Skill nemá být jeden recap tool. Má být builder framework pro systém, který umí:
- logovat jídlo a pití,
- přijímat biometriky z libovolného zdroje,
- ukládat canonical event data,
- počítat odvozené denní a trendové stavy,
- generovat průběžné a denní sumarizace,
- držet konzervativní zdravotní guardraily.

## Product framing

Neprodávat jako:
- Oura skill
- sleep recap skill
- medical AI

Prodávat jako:
- blueprint pro osobního health copilot agenta,
- reusable architecture pro food / hydration / biometrics / summaries,
- generic private wellness tracking system.

## Recommended skill name

`personal-health-copilot-builder`

Alternatives:
- `health-tracking-system-builder`
- `nutrition-recovery-copilot-builder`

## Scope v1

### In scope
- canonical data model
- storage design
- ingestion patterns pro manual + generic importy
- summary/report architecture
- health safety boundaries
- implementation plan
- bootstrap folder/file structure
- optional media recap layer jako presentation module, ne core

### Out of scope
- vendor-specific deep integrations jako primary path
- diagnosis / treatment recommendations
- hard-coded Oura / Apple Health assumptions
- rich UI product
- enterprise clinical workflows

## Core design principles

1. Domain-first, not vendor-first
2. Canonical storage before summaries
3. Deterministic computation, not arithmetic in prose
4. Separation of raw / normalized / derived / presentation layers
5. Conservative health language
6. Configurable connectors, not source-specific assumptions

## Target architecture

### Layer 1 — Domain model
Canonical entities:
- meal_event
- drink_event
- biometric_measurement
- sleep_session
- activity_event
- symptom_event
- medication_event
- daily_note

### Layer 2 — Ingestion
Supported patterns:
- manual text input
- photo-assisted meal entry
- json import
- csv import
- generic wearable import
- webhook / external sync adapter

### Layer 3 — Computation
Derived outputs:
- daily totals
- running day status
- baseline comparisons
- simple trends
- uncertainty-aware summaries

### Layer 4 — Presentation
Outputs:
- short text recap
- markdown daily report
- cards
- optional vertical video recap

## Required deliverables when the skill is used

The agent should produce:
1. system goal + scope
2. assumptions + constraints
3. canonical data model
4. storage layout
5. ingestion flows
6. derived-report flows
7. safety boundaries
8. implementation plan
9. concrete starter files

## Good default stack

For a local-first agent workspace:
- append-friendly event logs for user-entered events
- normalized json/jsonl or sqlite for canonical storage
- generated markdown reports for review
- scripts for deterministic calculations
- optional media renderer behind a clean interface

## Anti-patterns the skill should explicitly prevent

- vendor-first schema design
- agent memory as source of truth
- summary-first design before storage
- mixing measured vs reported vs inferred data
- hidden arithmetic inside freeform responses
- overconfident health interpretation
- persona work before architecture is stable

## Suggested file layout the skill should help create

```text
project/
  AGENTS.md
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
    data-model.md
    safety-boundaries.md
    operating-model.md
```

## Suggested first implementation milestones

### Milestone 1
- define scope
- define data model
- create storage layout
- create manual logging flow

### Milestone 2
- add deterministic totals and reports
- add basic daily summaries
- add baseline/trend computation

### Milestone 3
- add adapters/connectors
- add presentation variants
- optionally add media recap layer

## Distribution position

This should be a builder skill that another agent can use to create a custom system for a user.

Core promise:
> Give this skill to your agent and it will help you build a portable personal health, nutrition, and recovery copilot with safe summaries and deterministic storage.
