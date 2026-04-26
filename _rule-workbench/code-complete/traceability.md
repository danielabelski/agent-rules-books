# Code Complete Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Dropped from `nano.md` as default or duplicated with stronger books: broad readability and generic comment hygiene.
- Kept when a rule changes construction discipline, defensive behavior, control-flow choice, or data representation decisions.
- Merged review, codegen, testing, and forbidden-pattern sections into fewer operational rules plus a checklist.

## Min mapping

- `M1` Prefer clarity and maintainability over cleverness. Source: `Purpose` (3-19), `Primary Directive` (20-34), `Forbidden Patterns / Cleverness over Clarity` (209-212).
- `M2` Keep routines cohesive, with simple interfaces and deliberate local scope. Source: `Routine Design Rules` (45-62), `Variable and Data Rules` (63-78).
- `M3` Use explicit validation, assertions, preconditions, postconditions, and deliberate error handling around trust boundaries and assumptions. Source: `Defensive Programming Rules` (96-110), `Error Handling Rules` (111-120), `Construction with Preconditions and Postconditions` (155-163).
- `M4` Prefer straightforward control flow; use table-driven or data-driven logic for stable mappings instead of repetitive branching. Source: `Control Flow Rules` (79-95), `Table-Driven and Data-Driven Rules` (121-129).
- `M5` Use richer types, constants, and clear data semantics instead of magic values and ambiguous mutable state. Source: `Variable and Data Rules` (63-78).
- `M6` Build incrementally and review against consistency, complexity, and defect risk instead of making large speculative jumps. Source: `Incremental Construction Rules` (182-190), `Review Rules` (191-206), `Forbidden Patterns` (207-231).

## Nano mapping

- `N1` Choose clarity over cleverness. Source: `Primary Directive` (20-34), `Forbidden Patterns / Cleverness over Clarity` (209-212).
- `N2` Keep routines cohesive and interfaces small. Source: `Routine Design Rules` (45-62).
- `N3` Validate external input and use assertions/contracts for programmer assumptions. Source: `Defensive Programming Rules` (96-110), `Construction with Preconditions and Postconditions` (155-163).
- `N4` Replace repetitive stable branching with table-driven logic when it clarifies the mapping. Source: `Control Flow Rules` (79-95), `Table-Driven and Data-Driven Rules` (121-129).
- `N5` Use constants or richer types instead of magic values and ambiguous state. Source: `Variable and Data Rules` (63-78).

## Intentional omissions

- `Comment Rules` (164-172) and `Coding Standards Rules` (173-181): useful, but mostly default under tight context.
- `Testing Rules` (252-260) and `Review Checklist` (261-278): collapsed into trigger rules and checklist.
