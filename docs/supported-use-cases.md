# Supported and unsupported use cases

## Good fit

This repository is a good fit for:
- personal nutrition tracking
- hydration tracking
- personal biometrics journaling
- sleep and recovery summaries
- local-first health and wellness workspaces
- agent-built systems that need canonical storage and deterministic reports

## Borderline but possible later

These may fit later, but should not define v1:
- richer dashboards
- cards and video summaries
- advanced connector ecosystems
- multi-user household workflows
- more complex long-term trend analysis

## Poor fit

This repository is a poor fit for:
- diagnostic medical products
- treatment recommendation engines
- emergency triage systems
- highly regulated clinical software
- architectures built entirely around one vendor export format

## Practical rule

If the system cannot still make sense after swapping out the input connector, the architecture is probably too vendor-specific.
