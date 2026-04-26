# Release It! Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Re-run under the generalized `PROCESS.md` on 2026-04-26 after adding `Process vs Book Diagnosis`.
- This rerun found no new process bug and no new book-specific miss; existing `min.md` and `nano.md` already preserve the book thesis and repeated micro-decisions.
- `min.md` and `nano.md` stayed unchanged on this rerun.
- Some detailed logging, metrics, and deployment wording stays compressed because the operational pressure already survives through timeout, retry, isolation, load, idempotency, and observability rules.

## Min mapping

Decision rules:

- `M1` Assume every dependency can fail, stall, or lie; timeouts are mandatory. Source: `Primary Directive` (21-35), `Stability Mindset Rules` (36-48), `Dependency Protection Rules / Timeouts Are Mandatory` (51-56).
- `M2` Retries must be bounded, disciplined, and safe under idempotency; avoid retry storms. Source: `Dependency Protection Rules / Retries Must Be Disciplined` (57-62), `State and Data Safety Rules` (111-132), `Forbidden Patterns / Retry Storms` (263-267).
- `M3` Isolate failure with circuit breakers, bulkheads, and fast failure instead of letting the whole system hang together. Source: `Circuit Breakers and Fast Failure` (63-67), `Bulkheads and Isolation` (68-80), `Forbidden Patterns / Blast-Radius Amplification` (278-282).
- `M4` Design for load explicitly with backpressure, rate limits, queues, and load shedding. Source: `Load and Capacity Rules` (81-110), `Forbidden Patterns / Collapse by Queue` (268-272).
- `M5` Protect state and resources with idempotency, validation, quotas, and cleanup discipline. Source: `State and Data Safety Rules` (111-132), `Resource Management Rules` (133-153), `Data Boundary Rules` (154-163).
- `M6` Make observability part of the design: enough logs, metrics, and signals to diagnose degraded behavior. Source: `Operational Visibility Rules` (164-195).
- `M7` Make startup, deployment, APIs, caches, and background work fail safely and degrade predictably. Source: `Deployment and Startup Rules` (196-205), `API and Contract Rules` (206-215), `Cache Rules` (216-229), `Background Work Rules` (230-239).

Trigger rules:

- `M8` When adding an external call, choose timeout, retry, and fallback behavior deliberately. Source: `Dependency Protection Rules` (49-80).
- `M9` When adding a queue or async job, define capacity limits, duplicate-safety, and failure handling. Source: `Load and Capacity Rules` (81-110), `Background Work Rules` (230-239).
- `M10` When adding a cache, decide what happens on miss, stampede, staleness, and invalidation failure. Source: `Cache Rules` (216-229).
- `M11` When adding a new endpoint or critical path, define overload behavior before traffic defines it for you. Source: `Load and Capacity Rules` (81-110), `API and Contract Rules` (206-215).

Final checklist:

- The checklist restates `M1`, `M2`, `M3`, `M4`, and `M6` as a final scan rather than introducing new rules.

## Nano mapping

Decision rules:

- `N1` Assume dependencies fail or stall and make timeouts mandatory. Source: `Stability Mindset Rules` (36-48), `Dependency Protection Rules / Timeouts Are Mandatory` (51-56).
- `N2` Retry only when the operation is safe under duplication and with bounds. Source: `Dependency Protection Rules / Retries Must Be Disciplined` (57-62), `State and Data Safety Rules / Idempotency` (119-132), `Forbidden Patterns / Retry Storms` (263-267).
- `N3` Isolate failure and shed load before collapse. Source: `Circuit Breakers and Fast Failure` (63-67), `Bulkheads and Isolation` (68-80), `Load and Capacity Rules` (81-110).
- `N4` Protect state and inputs with idempotency, validation, and resource limits. Source: `State and Data Safety Rules` (111-132), `Resource Management Rules` (133-153), `Data Boundary Rules` (154-163).
- `N5` Design observability and background operations as first-class operational concerns. Source: `Operational Visibility Rules` (164-195), `Background Work Rules` (230-239).

Trigger rules:

- `N6` When adding an external call, choose timeout and retry behavior. Source: `Dependency Protection Rules` (49-80).
- `N7` When adding a queue or job, define duplicate-safety and capacity limits. Source: `Load and Capacity Rules` (81-110), `Background Work Rules` (230-239).
- `N8` When adding a cache or endpoint, define failure and overload behavior. Source: `Cache Rules` (216-229), `API and Contract Rules` (206-215).

Final checklist:

- The checklist restates `N1`, `N2`, `N3`, and `N5` as a final scan rather than introducing new rules.

## Section coverage review

- `Purpose` (3-20): framing merged into `When to use`, `Primary bias to correct`, and `M1`-`M4`.
- `Primary Directive` (21-35): covered by `M1` and `M2`.
- `Stability Mindset Rules` (36-48): covered by `M1` and `N1`.
- `Dependency Protection Rules` (49-80): covered by `M1`, `M2`, `M3`, `M8`, `N1`, `N2`, and `N6`.
- `Load and Capacity Rules` (81-110): covered by `M4`, `M9`, `M11`, `N3`, and `N7`.
- `State and Data Safety Rules` (111-132): covered by `M2`, `M5`, `N2`, and `N4`.
- `Resource Management Rules` (133-153): covered by `M5` and `N4`.
- `Data Boundary Rules` (154-163): covered by `M5` and `N4`.
- `Operational Visibility Rules` (164-195): covered by `M6` and `N5`.
- `Deployment and Startup Rules` (196-205): covered by `M7`.
- `API and Contract Rules` (206-215): covered by `M7`, `M11`, and `N8`.
- `Cache Rules` (216-229): covered by `M7`, `M10`, and `N8`.
- `Background Work Rules` (230-239): covered by `M7`, `M9`, `N5`, and `N7`.
- `Review Rules` (240-256): covered by `M1`-`M7`; collapsed into trigger rules and checklist.
- `Forbidden Patterns` (257-283): covered by `M2`, `M3`, `M4`, `N2`, and `N3`.
- `Code Generation Rules` (284-304): covered by `M1`-`M7`; standalone prose is intentionally lost.
- `Testing Rules` (305-315): covered by `M2`, `M3`, `M4`, and `M6`; collapsed into trigger rules and checklist.
- `Review Checklist` (316-333): covered by `M1`, `M2`, `M3`, `M4`, and `M6`; collapsed into the final checklist.
- `Final Instruction` (334-343): covered by `M1`, `M3`, `M4`, and `M6`.
