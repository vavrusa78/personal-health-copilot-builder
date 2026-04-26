# Operating model

## Data flow

1. Raw input arrives from manual logging or import.
2. Input is normalized into canonical events.
3. Deterministic scripts compute daily totals and summary state.
4. Reports are regenerated.
5. Presentation layers read only from derived or canonical artifacts.

## Golden rules

- Never compute totals only inside prose.
- Never use memory files as canonical health storage.
- Keep the system auditable and easy to inspect.
