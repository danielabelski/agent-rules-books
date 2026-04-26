# Designing Data-Intensive Applications: Nano

## When to use

Use when data correctness and distributed write semantics matter more than local code style.

## Primary bias to correct

Hidden data contracts are still contracts.

## Decision rules

- Give each fact a clear source of truth and owner.
- State the consistency contract for each write path.
- Make retried or replayed work idempotent; do not promise exactly-once casually.
- Treat schemas, events, and service boundaries as versioned contracts.
- Treat caches and derived data as secondary views, never the source of truth.

## Trigger rules

- When adding retries or consumers, prove duplicate safety.
- When changing schemas or events, plan compatibility.
- When writing the same truth in multiple places, define the authoritative path.

## Final checklist

- Clear owner?
- Explicit consistency?
- Replay-safe?
