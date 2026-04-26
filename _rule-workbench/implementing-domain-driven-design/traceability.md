# Implementing Domain-Driven Design Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Re-run under the generalized `PROCESS.md` on 2026-04-26 after adding `Process vs Book Diagnosis`.
- Manual fix on 2026-04-26 restored ubiquitous-language pressure as an explicit trigger in `min.md` and `nano.md`.
- This was treated as a book-specific miss, not a `PROCESS.md` change: the source makes naming and one-term-per-concept discipline operational at implementation level.
- Detailed review, testing, and repeated explanatory prose stay compressed because the operational pressure already survives through context boundaries, aggregate discipline, repository shape, context integration, and now explicit naming pressure.

## Min mapping

Decision rules:

- `M1` Treat bounded contexts as mandatory implementation boundaries and keep context maps explicit. Source: `Strategic Design Rules` (37-63), especially `Bounded Context Is Mandatory` (39-44) and `Context Mapping Is a Design Artifact` (45-50).
- `M2` Protect the core domain and keep simpler areas simpler. Source: `Core Domain Protection` (51-63), `Practical Simplicity Rule` (224-237).
- `M3` Treat aggregates as consistency boundaries, enforce aggregate-root discipline, and default to one aggregate per transaction. Source: `Aggregate Rules of Thumb` (78-109).
- `M4` Reference other aggregates by identity and use explicit domain events or application services for cross-aggregate and cross-context coordination. Source: `Aggregate Rules of Thumb / Reference Other Aggregates by Identity` (92-96), `Domain Event Rules` (146-161), `Application Service Rules` (162-176).
- `M5` Use entities and value objects deliberately, with immutable value objects and valid model construction. Source: `Entity and Value Object Rules` (110-129).
- `M6` Keep repositories focused on aggregate access and keep application services as coordinators rather than domain-rule containers. Source: `Repository Rules` (130-145), `Application Service Rules` (162-176).
- `M7` Use anti-corruption layers and explicit identity translation across contexts. Source: `Module and Package Rules` (177-191), `Context Integration Rules` (192-213), `Multi-Tenancy and Identity Discipline` (214-223).

Trigger rules:

- `M8` When a transaction wants to update multiple aggregates synchronously, re-check whether the invariant is truly immediate. Source: `Aggregate Rules of Thumb` (78-109).
- `M9` When code starts navigating across aggregate internals, replace graph coupling with identity references and coordination. Source: `Aggregate Rules of Thumb` (92-109), `Domain Event Rules` (146-161).
- `M10` When one context starts reusing another context's terms or model types directly, add translation instead of sharing the model. Source: `Strategic Design Rules` (37-63), `Context Integration Rules` (192-213).
- `M11` When a repository API starts looking generic and pattern-driven, narrow it back to aggregate needs. Source: `Repository Rules` (130-145).
- `M12` When names drift to generic technical placeholders or one term starts carrying multiple meanings inside a context, rename back to one domain term per concept across code, tests, commands, events, and repositories. Source: `Ubiquitous Language Rules` (64-77).

Final checklist:

- The checklist restates `M1`, `M3`, `M6`, `M7`, and `M12` as a final scan rather than introducing new rules.

## Nano mapping

Decision rules:

- `N1` Bounded contexts are real implementation boundaries, not documentation only. Source: `Strategic Design Rules` (37-63).
- `N2` Aggregates are consistency boundaries and default to one aggregate per transaction. Source: `Aggregate Rules of Thumb` (78-109).
- `N3` Reference other aggregates by identity and coordinate across them with events or application services. Source: `Aggregate Rules of Thumb` (92-109), `Domain Event Rules` (146-161), `Application Service Rules` (162-176).
- `N4` Keep repositories focused on aggregates and keep application services thin. Source: `Repository Rules` (130-145), `Application Service Rules` (162-176).
- `N5` Translate explicitly across contexts with anti-corruption layers where meanings differ. Source: `Context Integration Rules` (192-213).

Trigger rules:

- `N6` When one transaction wants many aggregates, revisit the invariant. Source: `Aggregate Rules of Thumb` (78-109).
- `N7` When object graph traversal crosses boundaries, switch to identity plus coordination. Source: `Aggregate Rules of Thumb` (92-109), `Domain Event Rules` (146-161).
- `N8` When context models leak into each other, add translation. Source: `Context Integration Rules` (192-213).
- `N9` When names drift to generic placeholders or one term starts meaning several things in the same context, rename back to the domain language. Source: `Ubiquitous Language Rules` (64-77).

Final checklist:

- The checklist restates `N1`, `N2`, `N5`, and `N9` as a final scan rather than introducing new rules.

## Section coverage review

- `Purpose` (3-20): framing merged into `When to use`, `Primary bias to correct`, and `M1`-`M3`.
- `Primary Directive` (21-36): covered by `M1`, `M3`, `M6`, and `M7`.
- `Strategic Design Rules` (37-63): covered by `M1`, `M2`, and `N1`.
- `Ubiquitous Language Rules` (64-77): covered by `M12` and `N9`.
- `Aggregate Rules of Thumb` (78-109): covered by `M3`, `M4`, `M8`, `M9`, `N2`, `N3`, `N6`, and `N7`.
- `Entity and Value Object Rules` (110-129): covered by `M5`.
- `Repository Rules` (130-145): covered by `M6`, `M11`, and `N4`.
- `Domain Event Rules` (146-161): covered by `M4`, `M9`, `N3`, and `N7`.
- `Application Service Rules` (162-176): covered by `M4`, `M6`, `N3`, and `N4`.
- `Module and Package Rules` (177-191): covered by `M7`.
- `Context Integration Rules` (192-213): covered by `M7`, `M10`, `N5`, and `N8`.
- `Multi-Tenancy and Identity Discipline` (214-223): covered by `M7`.
- `Practical Simplicity Rule` (224-237): covered by `M2`.
- `Code Generation Rules` (238-260): covered by `M1`, `M3`, `M5`, `M6`, and `M7`.
- `Review Rules` (261-276): covered by `M1`, `M3`, `M6`, `M7`, and `M12`; collapsed into trigger rules and checklist.
- `Testing Rules` (277-288): covered by `M3`, `M5`, and `M6`; collapsed into trigger rules and checklist.
- `Review Checklist` (289-306): covered by `M1`, `M3`, `M6`, `M7`, and `M12`; collapsed into the final checklist.
- `Final Instruction` (307-316): covered by `M1`, `M3`, `M6`, `M7`, and `M12`.
