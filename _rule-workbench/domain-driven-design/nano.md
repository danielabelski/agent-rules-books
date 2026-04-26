# Domain-Driven Design: Nano

## When to use

Use when you need a small always-on DDD bias that still changes modeling choices.

## Primary bias to correct

Generic plumbing is not a domain model.

## Decision rules

- Use DDD only where the domain needs a deep model.
- Use ubiquitous language and make implicit concepts explicit.
- Model bounded contexts and do not share one model across different meanings.
- Protect invariants inside expressive entities, value objects, and small aggregates.
- Keep application orchestration thin, infrastructure outside, and translation explicit at boundaries.
- Do not do fake DDD: no anemic model, ORM-driven design, or pattern cargo cult.

## Trigger rules

- When language is fuzzy, refine the model before coding more flows.
- When transactions sprawl, revisit the aggregate or context boundary.
- When storage shape drives the model, add translation and reclaim the domain.

## Final checklist

- Real domain language?
- Clear context boundary?
- Invariants inside the model?
