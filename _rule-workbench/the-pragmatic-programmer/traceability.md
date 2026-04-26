# The Pragmatic Programmer Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Dropped from `nano.md` as secondary: some broad communication, tooling, and review detail that does not directly shift the main engineering decisions.
- Kept whenever a rule changes knowledge ownership, orthogonality, delivery strategy, automation, or prototype discipline.
- Merged overlapping review, forbidden-pattern, codegen, and testing content into fewer pragmatic operating rules.

## Min mapping

- `M1` Own the result and think beyond the local edit. Source: `Core Pragmatic Principles` (36-54), especially `Own the Result` (38-42) and `Think Beyond the Local Edit` (43-47).
- `M2` Treat DRY as one authoritative place per piece of knowledge, not mere text deduplication. Source: `DRY Rules` (55-72), `Forbidden Patterns / Knowledge Duplication` (233-236).
- `M3` Preserve orthogonality so changes stay local and decisions do not fan out across unrelated parts. Source: `Orthogonality Rules` (73-86), `Forbidden Patterns / Non-Orthogonal Design` (237-240).
- `M4` Use tracer bullets and prototypes intentionally; learn quickly, but do not fossilize prototypes into production design. Source: `Tracer Bullets and Iterative Delivery` (87-100), `Prototyping Rules` (101-109), `Forbidden Patterns / Prototype Fossilization` (245-248).
- `M5` Automate repeatable work and shorten feedback loops. Source: `Automation Rules` (110-123), `Feedback Loop Rules` (124-133), `Forbidden Patterns / Manual Everything` (241-244).
- `M6` Use explicit contracts, assertions, and recovery choices where failure matters. Source: `Design by Contract and Assertions` (134-147), `Error Handling and Recovery` (148-156).
- `M7` Apply the broken windows rule: leave touched code slightly better than you found it. Source: `Broken Windows Rule` (203-211).

## Nano mapping

- `N1` Own the result beyond the local edit. Source: `Core Pragmatic Principles` (36-54).
- `N2` DRY means one authoritative place per piece of knowledge. Source: `DRY Rules` (55-72).
- `N3` Preserve orthogonality so changes stay local. Source: `Orthogonality Rules` (73-86).
- `N4` Use tracer bullets and prototypes to learn quickly, but do not fossilize them. Source: `Tracer Bullets and Iterative Delivery` (87-100), `Prototyping Rules` (101-109), `Prototype Fossilization` (245-248).
- `N5` Automate repeatable work and shorten feedback loops. Source: `Automation Rules` (110-123), `Feedback Loop Rules` (124-133).

## Intentional omissions

- Detailed naming, text/data, tooling, and estimation advice: useful, but less decision-changing under tight context.
- `Testing Rules` (269-277) and `Review Checklist` (278-293): collapsed into triggers and checklist.
