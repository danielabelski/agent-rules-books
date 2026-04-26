# Clean Code Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Dropped from `minimal.md` as default agent behavior: most formatting, generic readability, and obvious test hygiene.
- Kept when a rule changes API shape, mutation semantics, naming consistency, comment policy, or smell-removal behavior.
- Merged overlapping function, smell, review, and hard-rule sections into fewer operational rules.

## Optimal mapping

- `O1` Use precise names and one term per concept; rename when code obscures meaning. Source: `Naming rules` (24-43), `Review checklist` (215-229).
- `O2` Keep functions cohesive, at one abstraction level, with minimal parameters; split boolean flags and mixed responsibilities. Source: `Function rules` (44-63).
- `O3` Separate commands from queries and eliminate hidden side effects. Source: `Function rules` (44-63), `Hard rules` (239-245).
- `O4` Use comments only for rationale, constraints, or external contracts; never as a bandage for bad structure. Source: `Comment rules` (64-80).
- `O5` Expose behavior instead of representation and avoid utility dumping grounds, train wrecks, and arbitrary data/behavior mixing. Source: `Objects, modules, and data structures` (93-103), `Class and module design` (104-114).
- `O6` When touching code, remove the smells blocking safe change: duplication, deep nesting, long parameter lists, primitive obsession, hidden dependency, or irrelevant side effects. Source: `Refactoring rules` (158-168), `Smells to detect and eliminate` (169-190), `Change workflow` (191-203).
- `O7` Wrap unstable external dependencies behind local boundaries when the core would otherwise learn their quirks. Source: `Boundaries and external dependencies` (126-133).

## Minimal mapping

- `M1` Use precise names and one term per concept. Source: `Naming rules` (24-43).
- `M2` Split boolean flags, mixed abstraction levels, and hidden side effects out of functions. Source: `Function rules` (44-63), `Hard rules` (239-245).
- `M3` Separate commands from queries. Source: `Function rules` (44-63).
- `M4` Use comments only for rationale or contracts, not to explain confusing code. Source: `Comment rules` (64-80).
- `M5` When touching code, remove the smell most likely to make the next change risky or confusing. Source: `Smells to detect and eliminate` (169-190), `Change workflow` (191-203).

## Intentional omissions

- `Formatting and structure` (81-92), much of `Tests` (134-147), and much of `Implementation preferences` (204-214): mostly default hygiene.
- `Output expectations` (230-238): presentation guidance, not core decision logic.
