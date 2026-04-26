# Publishing and portability

## Recommended public shape

Use a public GitHub repo as the canonical home.
Treat the OpenClaw skill as one packaging target, not the only form.

## Good repo shape

- `/skill/` or `/openclaw-skill/` for SKILL.md packaging assets
- `/starter-project/` for generic scaffold
- `/docs/` for architecture and safety notes
- `/examples/` for sample canonical events and outputs

## Cross-agent compatibility

To work well with Codex, Claude Code, or similar agent tools:
- keep the architecture docs generic
- avoid OpenClaw-only assumptions in the core docs
- put OpenClaw-specific packaging in a subfolder
- define explicit input/output contracts
- include starter files the agent can copy into a new repo

## Positioning

Recommended message:
- generic health copilot builder
- local-first and vendor-agnostic
- deterministic summaries
- conservative health guardrails

## Important caution

Do not make the public repo depend on private paths, private credentials, or one specific wearable vendor.
