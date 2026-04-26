# Personal Health Copilot Builder

Build a portable personal health, nutrition, hydration, biometrics, and recovery copilot without vendor lock-in.

This repository is designed for agentic coding workflows, including OpenClaw, Codex, Claude Code, Claude CoWork, and similar tools.

## Status

Early public draft. The architecture, starter scaffold, and OpenClaw skill packaging are already in place. The repository now includes an Apache-2.0 license; the main remaining work before publishing is a final review of wording, positioning, and what you want to promise in v1.

## What this repository is

This is a **builder framework** for creating local-first health copilot systems that can:
- log food and hydration,
- accept biometrics from generic sources,
- maintain canonical structured storage,
- compute deterministic derived state,
- generate safe daily or weekly summaries,
- optionally add presentation layers such as cards or video.

## What this repository is not

This repository is not intended to be:
- an Oura-only integration,
- an Apple Health-only integration,
- a diagnostic medical system,
- a single prompt with no underlying storage model,
- a brittle one-user setup tied to private paths or one specific connector.

## Good fit

Use this repo when you want your agent to help create:
- a food and hydration tracker,
- a biometrics and recovery summary system,
- a portable health journaling workspace,
- a generic personal wellness copilot.

## Design principles

- domain-first, not vendor-first
- local-first and inspectable
- raw / canonical / derived / presentation separation
- deterministic calculations instead of hidden arithmetic in prose
- conservative health language and no diagnosis framing

## Repository layout

- `docs/` — architecture, data model, safety boundaries, publishing notes, supported use cases, usage notes
- `starter-project/` — copyable starter scaffold for a local-first health copilot workspace
- `examples/` — sample canonical events and sample outputs
- `openclaw-skill/` — OpenClaw skill packaging for the builder workflow

## Quick start

### Generic agent workflow

1. Read `docs/blueprint-v1.md`.
2. Copy `starter-project/` into a new workspace or repository.
3. Adapt the canonical model and ingestion paths to the user.
4. Implement deterministic calculations before writing smart summaries.
5. Keep health guardrails intact.

### OpenClaw workflow

1. Use the skill in `openclaw-skill/`.
2. Let the agent design the system in this order:
   - scope
   - canonical model
   - storage
   - ingestion
   - derived reports
   - safety boundaries
   - smallest useful v1

## Supported v1 shape

A strong v1 usually includes:
- meal logging,
- hydration logging,
- generic biometrics ingestion,
- canonical event storage,
- deterministic day totals,
- morning or evening summaries.

Leave richer media presentation, advanced connectors, and more sensitive health workflows for later versions.

## Safety note

This repository is for tracking, summarization, and cautious interpretation. It should not be positioned as a diagnosis engine or treatment system.

## Cross-agent portability

The repository is intentionally generic. OpenClaw-specific packaging lives in `openclaw-skill/` so the rest of the repository can stay usable for Codex, Claude Code, Claude CoWork, and similar environments.

## Publish checklist

See `docs/publish-checklist.md`.

## License

Apache-2.0.
