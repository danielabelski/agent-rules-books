# Domain-Driven Design Distilled Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Re-run under the generalized `PROCESS.md` on 2026-04-26 after adding `Process vs Book Diagnosis`.
- This rerun found no new process bug and no new book-specific miss; existing `min.md` and `nano.md` already preserve the book thesis and repeated micro-decisions.
- `min.md` and `nano.md` stayed unchanged on this rerun.
- Collaboration, review, and per-pattern narration stay compressed because the operational DDD pressure already survives through context boundaries, language, aggregates, thin services, and anti-ceremony rules.

## Min mapping

Decision rules:

- `M1` Start with subdomains and bounded contexts and do not apply DDD uniformly everywhere. Source: `Strategic Rules` (38-69), `Practicality Rules` (197-210).
- `M2` Use one ubiquitous language per bounded context across code and conversation. Source: `Ubiquitous Language Rules` (70-87).
- `M3` Use tactical patterns only when they express domain meaning: entities, value objects, aggregates, repositories, events, and domain services are tools, not ceremony. Source: `Tactical Pattern Rules` (88-139).
- `M4` Keep aggregates small and centered on real invariants and transactional consistency. Source: `Aggregate Minimalism Rules` (140-154).
- `M5` Keep application services thin; the domain model owns business rules and infrastructure stays outside. Source: `Application Service Rules` (155-168), `Architecture and Infrastructure Rules` (169-182).
- `M6` Stay practical: use richer modeling where complexity earns it and simpler styles where it does not. Source: `Practicality Rules` (197-210).

Trigger rules:

- `M7` When business language is fuzzy or overloaded, pause and sharpen the vocabulary before adding more code. Source: `Ubiquitous Language Rules` (70-87).
- `M8` When a transaction wants to mutate many roots at once, revisit the aggregate boundary or the consistency requirement. Source: `Tactical Pattern Rules / Aggregates` (106-114), `Aggregate Minimalism Rules` (140-154).
- `M9` When a service starts holding domain decisions, move that logic into the model or make the missing concept explicit. Source: `Tactical Pattern Rules` (88-139), `Application Service Rules` (155-168).
- `M10` When DDD jargon appears without a real domain reason, simplify. Source: `Practicality Rules` (197-210).

Final checklist:

- The checklist restates `M1`, `M2`, `M4`, and `M5` as a final scan rather than introducing new rules.

## Nano mapping

Decision rules:

- `N1` Start with subdomains and bounded contexts and do not apply DDD everywhere. Source: `Strategic Rules` (38-69), `Practicality Rules` (197-210).
- `N2` Use one ubiquitous language for the context. Source: `Ubiquitous Language Rules` (70-87).
- `N3` Put invariants inside small aggregates and do not spread one transaction across many roots by default. Source: `Tactical Pattern Rules / Aggregates` (106-114), `Aggregate Minimalism Rules` (140-154).
- `N4` Keep application services thin and keep business rules in the domain model. Source: `Application Service Rules` (155-168).
- `N5` Use DDD patterns only when they clarify domain meaning, not as ceremony. Source: `Tactical Pattern Rules` (88-139), `Practicality Rules` (197-210).

Trigger rules:

- `N6` When language is fuzzy, sharpen terms before coding. Source: `Ubiquitous Language Rules` (70-87).
- `N7` When one transaction wants many roots, revisit the aggregate. Source: `Aggregate Minimalism Rules` (140-154).
- `N8` When a service holds decisions, move them into the model. Source: `Application Service Rules` (155-168), `Tactical Pattern Rules` (131-139).

Final checklist:

- The checklist restates `N1`, `N2`, and `N3` as a final scan rather than introducing new rules.

## Section coverage review

- `Purpose` (3-19): framing merged into `When to use`, `Primary bias to correct`, and `M1`.
- `Primary Directive` (20-37): covered by `M1`, `M3`, and `M6`.
- `Strategic Rules` (38-69): covered by `M1` and `N1`.
- `Ubiquitous Language Rules` (70-87): covered by `M2`, `M7`, `N2`, and `N6`.
- `Tactical Pattern Rules` (88-139): covered by `M3`, `M8`, `M9`, `N3`, `N5`, and `N8`.
- `Aggregate Minimalism Rules` (140-154): covered by `M4`, `M8`, `N3`, and `N7`.
- `Application Service Rules` (155-168): covered by `M5`, `M9`, `N4`, and `N8`.
- `Architecture and Infrastructure Rules` (169-182): covered by `M5`.
- `Collaboration Rules` (183-196): covered by `M2` and `M5`; standalone collaboration phrasing is intentionally lost.
- `Practicality Rules` (197-210): covered by `M1`, `M6`, `M10`, `N1`, and `N5`.
- `Code Generation Rules` (211-229): covered by `M1`-`M6`; standalone prose is intentionally lost.
- `Review Rules` (230-246): covered by `M1`-`M6`; collapsed into trigger rules and checklist.
- `Testing Rules` (247-256): covered by `M4` and `M5`; collapsed into trigger rules and checklist.
- `Review Checklist` (257-273): covered by `M1`, `M2`, `M4`, and `M5`; collapsed into the final checklist.
- `Final Instruction` (274-283): covered by `M1`, `M4`, `M5`, and `M6`.
