# Safety boundaries

## Core posture

This system is for tracking, summaries, and cautious interpretation. It is not a diagnosis engine.

## Required rules

- Separate measured data from user-reported data.
- Separate imported source data from agent inference.
- State uncertainty directly.
- Do not overinterpret sparse or noisy signals.
- Do not present health guesses as facts.
- Recommend professional review for acute, risky, or unclear situations.

## Language rules

Prefer:
- "signal"
- "trend"
- "orientační"
- "pravděpodobně"
- "data naznačují"

Avoid:
- definitive diagnosis language
- treatment instructions without clear justification
- false precision from one snapshot

## Risk topics

Escalate carefully when the user reports:
- chest pain
- breathing problems
- fainting
- severe neurological symptoms
- severe allergic reactions
- other urgent states

## System design implication

Guardrails belong in the architecture, prompts, and reporting logic, not only in the final chat wording.
