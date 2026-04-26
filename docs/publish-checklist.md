# Publish checklist

## Must do before public release

- [x] Choose a license (Apache-2.0).
- [x] Remove any private paths, private names, or environment-specific assumptions that should not be public.
- [x] Re-read `README.md` from the perspective of an outsider.
- [x] Confirm that `starter-project/` contains only generic placeholders.
- [x] Confirm that `examples/` contain no private or identifying data.
- [x] Publish OpenClaw packaging in the same repo under `openclaw-skill/`, while keeping the rest of the repository generic.

## Strongly recommended

- [ ] Add one end-to-end example flow in `docs/` or `examples/`.
- [x] Add a short section on supported and unsupported use cases.
- [x] Add one concrete "build this for me" example prompt for agent workflows.
- [x] Decide on naming consistency: health, nutrition, hydration, biometrics, and recovery as the primary vocabulary.
- [x] Do one final pass on medical-risk wording.

## Nice to have

- [ ] Add screenshots or output previews later.
- [ ] Add issue templates for connector requests.
- [ ] Add a simple roadmap.

## Current blocker

There is no hard technical blocker now. The remaining work is editorial: one final pass on wording, positioning, and what exactly you want to promise publicly in v1.
