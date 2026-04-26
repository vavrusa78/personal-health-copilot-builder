# Publishing and portability

## Recommended public shape

Use this GitHub repository as the canonical home.
Treat the OpenClaw skill as one packaging target, not the only form.

## Why this layout

- `docs/` stays generic and readable
- `starter-project/` is easy for agents to copy into a fresh workspace
- `openclaw-skill/` keeps OpenClaw packaging isolated
- other agent tools can use the same repo without inheriting platform-specific assumptions

## Cross-agent compatibility rules

- keep architecture docs generic
- avoid private paths and credentials
- define explicit input/output contracts
- treat vendor adapters as optional extensions
- keep canonical storage independent from one specific data source

## Suggested future additions

- `examples/sample-day/`
- `examples/sample-week/`
- a public issue template for new connectors
- one repo-level license decision before publishing
