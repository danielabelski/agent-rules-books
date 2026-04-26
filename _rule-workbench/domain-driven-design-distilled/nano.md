# Domain-Driven Design Distilled: Nano

## When to use

Use when you need lightweight DDD guidance that still changes modeling decisions.

## Primary bias to correct

DDD is for domain complexity, not for decoration.

## Decision rules

- Start with subdomains and bounded contexts; do not apply DDD everywhere.
- Use one ubiquitous language for each context.
- Put invariants inside small aggregates.
- Keep application services thin and business rules in the domain model.
- Use DDD patterns only when they clarify domain meaning.

## Trigger rules

- When language is fuzzy, sharpen terms before coding.
- When one transaction wants many roots, revisit the aggregate.
- When a service holds decisions, move them into the model.

## Final checklist

- Clear context?
- Clear language?
- Clear invariant boundary?
