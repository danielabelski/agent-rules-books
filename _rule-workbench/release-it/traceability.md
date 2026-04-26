# Release It! Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Dropped from `nano.md` as secondary: some detailed logging, metrics, and deployment wording that is still represented in stronger operational rules.
- Kept whenever a rule changes timeout, retry, isolation, load, idempotency, resource, or observability decisions.
- Merged review, forbidden-pattern, codegen, and testing sections into a smaller reliability doctrine plus triggers.

## Min mapping

- `M1` Assume dependencies can fail, stall, or lie; timeouts are mandatory. Source: `Primary Directive` (21-35), `Stability Mindset Rules` (36-48), `Dependency Protection Rules / Timeouts Are Mandatory` (51-56).
- `M2` Retries must be bounded, disciplined, and safe under idempotency; avoid retry storms. Source: `Dependency Protection Rules / Retries Must Be Disciplined` (57-62), `State and Data Safety Rules` (111-132), `Forbidden Patterns / Retry Storms` (263-267).
- `M3` Isolate failure with circuit breakers, bulkheads, and fast failure instead of letting the whole system hang together. Source: `Circuit Breakers and Fast Failure` (63-67), `Bulkheads and Isolation` (68-80), `Forbidden Patterns / Blast-Radius Amplification` (278-282).
- `M4` Design for load explicitly with backpressure, rate limits, queues, and load shedding. Source: `Load and Capacity Rules` (81-110), `Forbidden Patterns / Collapse by Queue` (268-272).
- `M5` Protect state and resources with idempotency, validation, quotas, and cleanup discipline. Source: `State and Data Safety Rules` (111-132), `Resource Management Rules` (133-153), `Data Boundary Rules` (154-163).
- `M6` Make observability part of the design: enough logs, metrics, and signals to diagnose degraded behavior. Source: `Operational Visibility Rules` (164-195).
- `M7` Make startup, deployment, APIs, caches, and background work fail safely and degrade predictably. Source: `Deployment and Startup Rules` (196-205), `API and Contract Rules` (206-215), `Cache Rules` (216-229), `Background Work Rules` (230-239).

## Nano mapping

- `N1` Assume dependencies fail or stall; timeouts are mandatory. Source: `Stability Mindset Rules` (36-48), `Timeouts Are Mandatory` (51-56).
- `N2` Retry only when the operation is safe under duplication and with bounds. Source: `Retries Must Be Disciplined` (57-62), `Idempotency` (119-132), `Retry Storms` (263-267).
- `N3` Isolate failure and shed load before collapse. Source: `Circuit Breakers and Fast Failure` (63-67), `Bulkheads and Isolation` (68-80), `Load and Capacity Rules` (81-110).
- `N4` Protect state and inputs with idempotency, validation, and resource limits. Source: `State and Data Safety Rules` (111-132), `Resource Management Rules` (133-153), `Data Boundary Rules` (154-163).
- `N5` Design observability and background operations as first-class operational concerns. Source: `Operational Visibility Rules` (164-195), `Background Work Rules` (230-239).

## Intentional omissions

- Some detailed logging and metrics sub-points are represented by the broader observability rule.
- `Testing Rules` (305-315) and `Review Checklist` (316-333): collapsed into triggers and checklist.
