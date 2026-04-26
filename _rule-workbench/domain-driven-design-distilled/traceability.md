# Domain-Driven Design Distilled Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Dropped from `minimal.md` as lower-yield: some collaboration and review phrasing that supports DDD but does not itself change model shape.
- Kept whenever a rule changes where DDD applies, how contexts are split, how aggregates are bounded, or where business rules live.
- Merged tactical pattern detail into a smaller set of modeling choices and triggers.

## Optimal mapping

- `O1` Start with subdomains and bounded contexts; do not apply DDD uniformly everywhere. Source: `Strategic Rules` (38-69), `Practicality Rules` (197-210).
- `O2` Use ubiquitous language consistently across code and conversation. Source: `Ubiquitous Language Rules` (70-87).
- `O3` Use tactical patterns only when they express domain meaning: entities, value objects, aggregates, repositories, domain events, domain services. Source: `Tactical Pattern Rules` (88-139).
- `O4` Keep aggregates small and centered on real invariants and transactional consistency. Source: `Aggregate Minimalism Rules` (140-154).
- `O5` Keep application services thin; the domain model owns business rules, infrastructure stays outside. Source: `Application Service Rules` (155-168), `Architecture and Infrastructure Rules` (169-182).
- `O6` Keep the approach practical: use richer modeling where complexity earns it and simpler styles where it does not. Source: `Practicality Rules` (197-210).

## Minimal mapping

- `M1` Start with subdomains and bounded contexts; do not apply DDD everywhere. Source: `Strategic Rules` (38-69), `Practicality Rules` (197-210).
- `M2` Use one ubiquitous language for the context. Source: `Ubiquitous Language Rules` (70-87).
- `M3` Put invariants inside small aggregates and do not spread one transaction across many roots by default. Source: `Tactical Pattern Rules / Aggregates` (106-114), `Aggregate Minimalism Rules` (140-154).
- `M4` Keep application services thin and keep business rules in the domain model. Source: `Application Service Rules` (155-168).
- `M5` Use DDD patterns only when they clarify domain meaning, not as ceremony. Source: `Tactical Pattern Rules` (88-139), `Practicality Rules` (197-210).

## Intentional omissions

- `Review Rules` (230-246) and `Testing Rules` (247-256): collapsed into triggers and checklist.
- Detailed per-pattern narration inside `Tactical Pattern Rules` (88-139): merged into a smaller tactical-pattern rule.
