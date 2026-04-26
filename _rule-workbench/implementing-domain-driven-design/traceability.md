# Implementing Domain-Driven Design Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Dropped from `nano.md` as lower-yield: some detailed review/test phrasing and repeated explanations around the same aggregate rules.
- Kept whenever a rule changes bounded-context implementation, aggregate consistency boundaries, repository/event usage, or context integration decisions.
- Merged the detailed aggregate subsections and context-integration subsections into fewer operational rules and triggers.

## Min mapping

- `M1` Treat bounded contexts as mandatory implementation boundaries and keep context maps explicit. Source: `Strategic Design Rules` (37-63), especially `Bounded Context Is Mandatory` (39-44) and `Context Mapping Is a Design Artifact` (45-50).
- `M2` Protect the core domain and keep simpler areas simpler. Source: `Core Domain Protection` (51-63), `Practical Simplicity Rule` (224-237).
- `M3` Treat aggregates as consistency boundaries, enforce aggregate-root discipline, and default to one aggregate per transaction. Source: `Aggregate Rules of Thumb` (78-109).
- `M4` Reference other aggregates by identity and use explicit domain events for cross-aggregate or cross-context reactions. Source: `Aggregate Rules of Thumb / Reference Other Aggregates by Identity` (92-96), `Domain Event Rules` (146-161).
- `M5` Use entities and value objects deliberately, with immutable value objects and valid model construction. Source: `Entity and Value Object Rules` (110-129).
- `M6` Keep repositories focused on aggregates and keep application services as coordinators rather than domain-rule containers. Source: `Repository Rules` (130-145), `Application Service Rules` (162-176).
- `M7` Use anti-corruption layers and explicit identity translation across contexts. Source: `Context Integration Rules` (192-213), `Module and Package Rules` (177-191), `Multi-Tenancy and Identity Discipline` (214-223).

## Nano mapping

- `N1` Bounded contexts are real implementation boundaries, not documentation only. Source: `Strategic Design Rules` (37-63).
- `N2` Aggregates are consistency boundaries; default to one aggregate per transaction. Source: `Aggregate Rules of Thumb` (78-109).
- `N3` Reference other aggregates by identity and coordinate across them with events or application services. Source: `Aggregate Rules of Thumb` (92-109), `Domain Event Rules` (146-161), `Application Service Rules` (162-176).
- `N4` Keep repositories focused on aggregates and keep application services thin. Source: `Repository Rules` (130-145), `Application Service Rules` (162-176).
- `N5` Translate explicitly across contexts with anti-corruption layers where meanings differ. Source: `Context Integration Rules` (192-213).

## Intentional omissions

- `Review Rules` (261-276), `Testing Rules` (277-288), and `Review Checklist` (289-306): collapsed into triggers and checklist.
- `Multi-Tenancy and Identity Discipline` (214-223): partly folded into the context-integration and identity-translation rule.
