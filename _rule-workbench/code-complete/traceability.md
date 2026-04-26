# Code Complete Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Re-run under the generalized `PROCESS.md` on 2026-04-26 after adding `Process vs Book Diagnosis`.
- Manual fix on 2026-04-26 restored explicit comment discipline as a trigger in `min.md` and `nano.md`.
- This was treated as a book-specific miss, not a `PROCESS.md` change: the source makes comment usefulness and anti-narration behavior operational, not merely stylistic.
- Broader coding-standards prose and review scaffolding still stay compressed because the main construction pressure survives through routine shape, data meaning, defensive programming, control-flow rules, and now explicit comment discipline.

## Min mapping

Decision rules:

- `M1` Treat construction quality as deliberate defect prevention and choose clarity, locality, and explicitness over cleverness. Source: `Purpose` (3-19), `Primary Directive` (20-34), `Foundational Construction Rules` (35-43), `Forbidden Patterns / Cleverness over Clarity` (209-212).
- `M2` Keep routines cohesive with one clear purpose and hard-to-misuse interfaces; separate setup, validation, computation, and side effects when concerns differ. Source: `Routine Design Rules` (45-62).
- `M3` Keep data meaning explicit with small scope, deliberate initialization, strong types, constants, and visible units or semantics. Source: `Variable and Data Rules` (63-78).
- `M4` Use explicit validation, assertions, preconditions, postconditions, and deliberate error handling around trust boundaries and assumptions. Source: `Defensive Programming Rules` (96-110), `Error Handling Rules` (111-120), `Construction with Preconditions and Postconditions` (155-163).
- `M5` Prefer straightforward control flow and use table-driven or data-driven logic for stable mappings when it clarifies the rule. Source: `Control Flow Rules` (79-95), `Table-Driven and Data-Driven Rules` (121-129).
- `M6` Keep classes and modules cohesive, hide incidental detail, and reduce coupling through clear contracts and limited knowledge. Source: `Class and Module Design Rules` (130-143), `Complexity Management Rules` (145-154).
- `M7` Build incrementally and review against defect risk, consistency, and rising complexity instead of making large speculative jumps. Source: `Incremental Construction Rules` (182-190), `Review Rules` (191-206), `Forbidden Patterns` (207-231).

Trigger rules:

- `M8` When input crosses a trust boundary, decide what is validated, asserted, rejected, or recovered from. Source: `Defensive Programming Rules` (96-110), `Error Handling Rules` (111-120).
- `M9` When a routine accumulates several phases or a long signature, split the responsibility or model the data more clearly. Source: `Routine Design Rules` (45-62), `Forbidden Patterns / Routine Bloat` (213-216).
- `M10` When a variable carries units, status, or lifecycle implicitly, turn that meaning into a clearer type, constant, or name. Source: `Variable and Data Rules` (63-78).
- `M11` When branching grows around a stable mapping, check whether a table or policy object would make the logic more inspectable. Source: `Control Flow Rules` (79-95), `Table-Driven and Data-Driven Rules` (121-129).
- `M12` When a clever shortcut saves lines but costs inspection effort, prefer the boring form. Source: `Primary Directive` (20-34), `Forbidden Patterns / Cleverness over Clarity` (209-212).
- `M13` When a comment explains obvious code, rewrite or delete it; keep comments for intent, rationale, contracts, and non-obvious facts. Source: `Comment Rules` (164-172).

Final checklist:

- The checklist restates `M1`, `M3`, `M4`, `M7`, and `M13` as a final scan rather than introducing new rules.

## Nano mapping

Decision rules:

- `N1` Choose clarity over cleverness. Source: `Primary Directive` (20-34), `Forbidden Patterns / Cleverness over Clarity` (209-212).
- `N2` Keep routines cohesive and interfaces small. Source: `Routine Design Rules` (45-62).
- `N3` Validate external input and use assertions or contracts for programmer assumptions. Source: `Defensive Programming Rules` (96-110), `Construction with Preconditions and Postconditions` (155-163).
- `N4` Keep invalid states visible and the normal path readable. Source: `Defensive Programming Rules` (96-110), `Error Handling Rules` (111-120).
- `N5` Replace repetitive stable branching with table-driven logic when it clarifies the mapping. Source: `Control Flow Rules` (79-95), `Table-Driven and Data-Driven Rules` (121-129).
- `N6` Use constants or richer types instead of magic values and ambiguous state. Source: `Variable and Data Rules` (63-78).

Trigger rules:

- `N7` When input crosses a trust boundary, decide what gets validated. Source: `Defensive Programming Rules` (96-110).
- `N8` When a routine mixes several phases, split the concerns. Source: `Routine Design Rules` (45-62).
- `N9` When branches multiply, consider a table. Source: `Control Flow Rules` (79-95), `Table-Driven and Data-Driven Rules` (121-129).
- `N10` When a value carries hidden meaning, model it. Source: `Variable and Data Rules` (63-78).
- `N11` When a comment explains obvious mechanics, rewrite the code or delete the comment. Source: `Comment Rules` (164-172).

Final checklist:

- The checklist restates `N1`, `N3`, `N4`, `N6`, and `N11` as a final scan rather than introducing new rules.

## Section coverage review

- `Purpose` (3-19): covered by `M1`.
- `Primary Directive` (20-34): covered by `M1`, `M12`, and `N1`.
- `Foundational Construction Rules` (35-43): covered by `M1`.
- `Routine Design Rules` (45-62): covered by `M2`, `M9`, `N2`, and `N8`.
- `Variable and Data Rules` (63-78): covered by `M3`, `M10`, `N6`, and `N10`.
- `Control Flow Rules` (79-95): covered by `M5`, `M11`, `N5`, and `N9`.
- `Defensive Programming Rules` (96-110): covered by `M4`, `M8`, `N3`, `N4`, and `N7`.
- `Error Handling Rules` (111-120): covered by `M4`, `M8`, and `N4`.
- `Table-Driven and Data-Driven Rules` (121-129): covered by `M5`, `M11`, `N5`, and `N9`.
- `Class and Module Design Rules` (130-143): covered by `M6`.
- `Complexity Management Rules` (145-154): covered by `M6` and `M7`.
- `Construction with Preconditions and Postconditions` (155-163): covered by `M4` and `N3`.
- `Comment Rules` (164-172): covered by `M13` and `N11`.
- `Coding Standards Rules` (173-181): covered by `M1` and `M7`; standalone wording is intentionally lost.
- `Incremental Construction Rules` (182-190): covered by `M7`.
- `Review Rules` (191-206): covered by `M7` and `M13`; collapsed into trigger rules and checklist.
- `Forbidden Patterns` (207-231): covered by `M1`, `M2`, `M4`, `M7`, `M9`, and `M12`.
- `Code Generation Rules` (232-251): covered by `M1`-`M6`; standalone prose is intentionally lost.
- `Testing Rules` (252-260): covered by `M4`, `M7`, `N3`, and `N4`; collapsed into trigger rules and checklist.
- `Review Checklist` (261-278): covered by `M1`, `M3`, `M4`, `M7`, and `M13`; collapsed into the final checklist.
- `Final Instruction` (279-288): covered by `M1`, `M4`, `M5`, and `N1`.
