# Designing Data-Intensive Applications Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Re-run under the generalized `PROCESS.md` on 2026-04-26 after adding `Process vs Book Diagnosis`.
- This rerun found no new process bug and no new book-specific miss; existing `min.md` and `nano.md` already preserve the book thesis and repeated micro-decisions.
- `min.md` and `nano.md` stayed unchanged on this rerun.
- Detailed testing and review phrasing stays compressed because the system-semantic pressure already survives through ownership, consistency, replay safety, schema contracts, and derived-data rules.

## Min mapping

Decision rules:

- `M1` Define a single source of truth and explicit data ownership for each fact. Source: `Data Model and Storage Rules` (50-71), `Source of Truth` (57-71).
- `M2` Make consistency and write semantics explicit and default to one local transaction or aggregate for immediate invariants. Source: `Consistency Rules` (72-93), `Transaction Rules` (176-189).
- `M3` Require idempotency and replay safety for retried, queued, or event-driven writes; reject casual exactly-once claims. Source: `Idempotency and Replay Rules` (94-107), `Forbidden Patterns / Exactly-Once Wishful Thinking` (231-234).
- `M4` Preserve ordering only where the product needs it and encode the ordering contract explicitly. Source: `Ordering Rules` (108-125).
- `M5` Treat events, logs, APIs, and schemas as durable contracts; evolve them compatibly and plan for mixed-version traffic and rebuilds. Source: `Event, Log, and Stream Rules` (126-146), `Schema Evolution Rules` (147-161), `API and Service Boundary Rules` (204-212).
- `M6` Treat derived data, caches, and indexes as secondary views that can lag or be rebuilt. Source: `Derived Data Rules` (190-203).
- `M7` Partition around locality and access patterns, not convenience, and make cross-partition costs visible. Source: `Partitioning and Locality Rules` (162-175), `Forbidden Patterns / Multi-Write Chaos` (239-242).

Trigger rules:

- `M8` When touching a write path, state the source of truth, consistency boundary, and failure semantics. Source: `Data Model and Storage Rules` (50-71), `Consistency Rules` (72-93), `Transaction Rules` (176-189).
- `M9` When adding retries, background jobs, or event consumers, prove the handler is idempotent under duplicate delivery and replay. Source: `Idempotency and Replay Rules` (94-107), `Forbidden Patterns / Exactly-Once Wishful Thinking` (231-234).
- `M10` When changing a schema or event, decide how older readers, newer writers, and rebuild paths will work. Source: `Event, Log, and Stream Rules` (126-146), `Schema Evolution Rules` (147-161), `Forbidden Patterns / Schema Drift by Accident` (243-249).
- `M11` When the design writes one business fact in multiple places, make the coordination contract explicit or collapse to one authoritative write. Source: `Source of Truth` (57-71), `Consistency Rules` (72-93), `Forbidden Patterns / Hidden Consistency Contract` (235-238), `Forbidden Patterns / Multi-Write Chaos` (239-242).

Final checklist:

- The checklist restates `M1`, `M2`, `M3`, and `M6` as a final scan rather than introducing new rules.

## Nano mapping

Decision rules:

- `N1` Give each fact a clear source of truth and owner. Source: `Data Model and Storage Rules` (50-71).
- `N2` State the consistency contract for each write path instead of implying it. Source: `Consistency Rules` (72-93), `Transaction Rules` (176-189).
- `N3` Make retried or replayed work idempotent and do not promise exactly-once casually. Source: `Idempotency and Replay Rules` (94-107), `Forbidden Patterns / Exactly-Once Wishful Thinking` (231-234).
- `N4` Treat schemas, events, and service boundaries as versioned contracts. Source: `Event, Log, and Stream Rules` (126-146), `Schema Evolution Rules` (147-161), `API and Service Boundary Rules` (204-212).
- `N5` Treat caches and derived data as secondary views, never the source of truth. Source: `Derived Data Rules` (190-203).

Trigger rules:

- `N6` When adding retries or consumers, prove duplicate safety. Source: `Idempotency and Replay Rules` (94-107).
- `N7` When changing schemas or events, plan compatibility. Source: `Schema Evolution Rules` (147-161), `Forbidden Patterns / Schema Drift by Accident` (243-249).
- `N8` When writing the same truth in multiple places, define the authoritative path. Source: `Source of Truth` (57-71), `Forbidden Patterns / Hidden Consistency Contract` (235-238), `Forbidden Patterns / Multi-Write Chaos` (239-242).

Final checklist:

- The checklist restates `N1`, `N2`, `N3`, and `N5` as a final scan rather than introducing new rules.

## Section coverage review

- `Purpose` (3-19): framing merged into `When to use`, `Primary bias to correct`, and `M1`-`M3`.
- `Primary Directive` (20-35): covered by `M2`, `M3`, and `N2`-`N4`.
- `Reliability Rules` (36-49): covered by `M2`, `M3`, `M5`, and `N2`-`N4`.
- `Data Model and Storage Rules` (50-71): covered by `M1`, `M8`, `N1`, and `N8`.
- `Consistency Rules` (72-93): covered by `M2`, `M8`, `M11`, `N2`, and `N8`.
- `Idempotency and Replay Rules` (94-107): covered by `M3`, `M9`, `N3`, and `N6`.
- `Ordering Rules` (108-125): covered by `M4`.
- `Event, Log, and Stream Rules` (126-146): covered by `M5`, `M10`, and `N4`.
- `Schema Evolution Rules` (147-161): covered by `M5`, `M10`, `N4`, and `N7`.
- `Partitioning and Locality Rules` (162-175): covered by `M7`.
- `Transaction Rules` (176-189): covered by `M2`, `M8`, and `N2`.
- `Derived Data Rules` (190-203): covered by `M6` and `N5`.
- `API and Service Boundary Rules` (204-212): covered by `M5` and `N4`.
- `Review Rules` (213-228): covered by `M1`-`M7`; collapsed into trigger rules and checklist.
- `Forbidden Patterns` (229-249): covered by `M3`, `M7`, `M9`, `M10`, `M11`, `N3`, `N7`, and `N8`.
- `Code Generation Rules` (250-268): covered by `M1`-`M7`; standalone prose is intentionally lost.
- `Testing Rules` (269-279): covered by `M2`, `M3`, `M5`, and `M6`; collapsed into trigger rules and checklist.
- `Review Checklist` (280-297): covered by `M1`, `M2`, `M3`, and `M6`; collapsed into the final checklist.
- `Final Instruction` (298-307): covered by `M1`, `M2`, `M3`, and `N2`-`N4`.
