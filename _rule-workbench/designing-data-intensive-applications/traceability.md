# Designing Data-Intensive Applications Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Dropped from `nano.md` as secondary: detailed testing and review phrasing that does not change system semantics by itself.
- Kept whenever a rule changes data ownership, consistency, retry, replay, ordering, schema, or derived-data decisions.
- Merged review, forbidden-pattern, and codegen sections into a smaller set of explicit data-contract rules and triggers.

## Min mapping

- `M1` Define a single source of truth and explicit data ownership for each fact. Source: `Data Model and Storage Rules` (50-71), `Source of Truth` (57-71).
- `M2` Make consistency and write semantics explicit; default to one local transaction or aggregate for immediate invariants. Source: `Consistency Rules` (72-93), `Transaction Rules` (176-189).
- `M3` Require idempotency and replay safety for retried, queued, or event-driven writes; reject casual exactly-once claims. Source: `Idempotency and Replay Rules` (94-107), `Forbidden Patterns / Exactly-Once Wishful Thinking` (231-234).
- `M4` Preserve ordering only where the product needs it and encode the ordering contract explicitly. Source: `Ordering Rules` (108-125).
- `M5` Treat events, logs, APIs, and schemas as durable contracts; evolve them compatibly and plan for rebuilds. Source: `Event, Log, and Stream Rules` (126-146), `Schema Evolution Rules` (147-161), `API and Service Boundary Rules` (204-212).
- `M6` Treat derived data, caches, and indexes as secondary views that can lag or be rebuilt. Source: `Derived Data Rules` (190-203).
- `M7` Partition around locality and access patterns, not convenience, and make cross-partition costs visible. Source: `Partitioning and Locality Rules` (162-175), `Forbidden Patterns / Multi-Write Chaos` (239-242).

## Nano mapping

- `N1` Give each fact a clear source of truth and owner. Source: `Data Model and Storage Rules` (50-71).
- `N2` State the consistency contract for each write path instead of implying it. Source: `Consistency Rules` (72-93), `Transaction Rules` (176-189).
- `N3` Make retried or replayed work idempotent; do not promise exactly-once casually. Source: `Idempotency and Replay Rules` (94-107), `Forbidden Patterns / Exactly-Once Wishful Thinking` (231-234).
- `N4` Treat schemas, events, and service boundaries as versioned contracts. Source: `Event, Log, and Stream Rules` (126-146), `Schema Evolution Rules` (147-161), `API and Service Boundary Rules` (204-212).
- `N5` Treat caches and derived data as secondary views, never the source of truth. Source: `Derived Data Rules` (190-203).

## Intentional omissions

- `Reliability Rules` (36-49): partially folded into idempotency and contract rules; deeper operational concerns live more directly in `release-it`.
- `Testing Rules` (269-279) and `Review Checklist` (280-297): collapsed into triggers and checklist.
