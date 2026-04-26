# Implementing Domain-Driven Design: Minimal

## When to use

Use when the main DDD implementation risks are aggregate sprawl and context leakage.

## Primary bias to correct

Consistency boundaries are more important than convenient object graphs.

## Decision rules

- Bounded contexts are real implementation boundaries.
- Aggregates are consistency boundaries; default to one aggregate per transaction.
- Reference other aggregates by identity and coordinate across them with events or application services.
- Keep repositories focused on aggregates and keep application services thin.
- Translate explicitly across contexts with anti-corruption layers where meanings differ.

## Trigger rules

- When one transaction wants many aggregates, revisit the invariant.
- When object graph traversal crosses boundaries, switch to identity plus coordination.
- When context models leak into each other, add translation.

## Final checklist

- Clear boundary?
- Clear invariant root?
- Clear translation?
