# Release It!: Nano

## When to use

Use when operational survivability matters and context is tight.

## Primary bias to correct

Production failure semantics must be designed, not discovered.

## Decision rules

- Assume dependencies fail or stall; timeouts are mandatory.
- Retry only when the operation is safe under duplication and with bounds.
- Isolate failure and shed load before collapse.
- Protect state and inputs with idempotency, validation, and resource limits.
- Design observability and background operations as first-class operational concerns.

## Trigger rules

- When adding an external call, choose timeout and retry behavior.
- When adding a queue or job, define duplicate-safety and capacity limits.
- When adding a cache or endpoint, define failure and overload behavior.

## Final checklist

- Timed out?
- Duplicate-safe?
- Isolated?
- Observable?
