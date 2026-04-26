# Refactoring: Nano

## When to use

Use when you need a small always-on refactoring discipline.

## Primary bias to correct

“Cleaning up” is not a license to rewrite.

## Decision rules

- Refactoring preserves observable behavior.
- Use small, verifiable steps; no big-bang rewrites.
- Get a safety net first.
- Refactor the smell that blocks change now, not every smell in sight.
- Keep refactoring and behavior change distinct when practical.

## Trigger rules

- When a patch mixes intents, split it.
- When structure is risky and untested, characterize first.
- When tempted to rewrite, find the next smaller safe move.

## Final checklist

- Same behavior?
- Small step?
- Safety net?
