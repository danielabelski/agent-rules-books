# A Philosophy of Software Design Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Re-run under the generalized `PROCESS.md` on 2026-04-26 after adding `Process vs Book Diagnosis`.
- This rerun found no new process bug and no further book-specific miss; the previously strengthened `min.md` already preserves the book's local-complexity pressure from `Function and Variable Rules`.
- `min.md` and `nano.md` stayed unchanged on this rerun.
- Generic review, testing, and codegen scaffolding stays compressed because the book's decision pressure is carried by depth, information hiding, interface design, and complexity movement.

## Min mapping

Decision rules:

- `M1` Treat complexity as the main design metric and reject line-count or cleverness as proxies. Source: `Purpose` (3-19), `Primary Directive` (21-34), `Core Complexity Rules` (36-56).
- `M2` Prefer deep modules and reject pass-through layers that do not hide meaningful complexity. Source: `Module Depth Rules` (57-80), `Forbidden Patterns / Shallow Decomposition` (247-252).
- `M3` Hide volatile details, internal data representation, bookkeeping, normalization, and messy edge cases behind stable interfaces. Source: `Information Hiding Rules` (81-95), `Pull Complexity Downward` (159-169), `Forbidden Patterns / Interface Leakage` (253-256).
- `M4` Design interfaces around client knowledge rather than implementation mechanics; avoid staged call sequences, flags, and mechanism leakage. Source: `Interface Design Rules` (96-117), `Error Handling and Exception Elimination` (144-158), `Special-General Decomposition` (218-230).
- `M5` Fix awkwardness strategically instead of adding tactical wrappers, proliferating special cases, or spreading complexity. Source: `Strategic Programming over Tactical Programming` (118-134), `General-Purpose vs Special-Purpose Modules` (135-143), `Forbidden Patterns / Tactical Complexity Debt` (257-260).
- `M6` Make temporal dependencies explicit and minimize order-sensitive behavior readers must reconstruct mentally. Source: `Temporal Decomposition Rules` (204-217), `Forbidden Patterns / Complexity Spread` (261-266).
- `M7` At function and variable level, keep meaning packed instead of exposing jump-heavy micro-steps or pass-through state. Source: `Function and Variable Rules` (189-203).
- `M8` Use comments only for contracts, invariants, or rationale that code cannot express cleanly. Source: `Comment Rules` (170-188).

Trigger rules:

- `M9` When adding a module, layer, service, or helper, prove it hides real complexity instead of renaming or forwarding it. Source: `Module Depth Rules` (57-80), `Forbidden Patterns / Shallow Decomposition` (247-252).
- `M10` When touching an API, check whether callers need too much context, too many steps, or knowledge of internals. Source: `Interface Design Rules` (96-117), `Error Handling and Exception Elimination` (144-158), `Special-General Decomposition` (218-230).
- `M11` When adding a special case, flag, or exception path, first ask whether the abstraction boundary is wrong. Source: `Strategic Programming over Tactical Programming` (118-134), `Special-General Decomposition` (218-230), `Forbidden Patterns / Tactical Complexity Debt` (257-260).
- `M12` When one change spreads across many files, look for missing information hiding, missing module depth, or temporal coupling. Source: `Information Hiding Rules` (81-95), `Pull Complexity Downward` (159-169), `Temporal Decomposition Rules` (204-217), `Forbidden Patterns / Complexity Spread` (261-266).
- `M13` When splitting a function or introducing a temporary only for style, check whether it improves understanding or only adds jumps and visible intermediate state. Source: `Function and Variable Rules` (189-203).

Final checklist:

- The checklist restates `M1`, `M3`, `M4`, and `M5` as a final scan rather than introducing new rules.

## Nano mapping

Decision rules:

- `N1` Optimize for lower cognitive load, not shorter files or fewer lines. Source: `Primary Directive` (21-34), `Core Complexity Rules` (36-56).
- `N2` Prefer deep modules and reject wrappers or layers that do not hide real complexity. Source: `Module Depth Rules` (57-80), `Forbidden Patterns / Shallow Decomposition` (247-252).
- `N3` Hide volatile details and messy edge handling below stable interfaces. Source: `Information Hiding Rules` (81-95), `Pull Complexity Downward` (159-169).
- `N4` Keep interfaces narrow and semantic; avoid staged APIs, flags, and mechanism leakage. Source: `Interface Design Rules` (96-117), `Special-General Decomposition` (218-230).
- `N5` When a change feels awkward, fix the design instead of layering tactical special cases. Source: `Strategic Programming over Tactical Programming` (118-134), `General-Purpose vs Special-Purpose Modules` (135-143).

Trigger rules:

- `N6` When adding a helper or layer, prove it removes complexity for callers. Source: `Module Depth Rules` (57-80), `Forbidden Patterns / Shallow Decomposition` (247-252).
- `N7` When an API requires sequencing knowledge, redesign the boundary. Source: `Interface Design Rules` (96-117), `Special-General Decomposition` (218-230).
- `N8` When one change spreads widely, look for hidden dependencies or the wrong abstraction. Source: `Information Hiding Rules` (81-95), `Temporal Decomposition Rules` (204-217), `Forbidden Patterns / Complexity Spread` (261-266).

Final checklist:

- The checklist restates `N1`, `N3`, and `N5` as a final scan rather than introducing new rules.

## Section coverage review

- `Purpose` (3-19): covered by `M1` and `N1`.
- `Primary Directive` (21-34): covered by `M1` and `N1`.
- `Core Complexity Rules` (36-56): covered by `M1` and `N1`.
- `Module Depth Rules` (57-80): covered by `M2`, `M9`, `N2`, and `N6`.
- `Information Hiding Rules` (81-95): covered by `M3`, `M12`, `N3`, and `N8`.
- `Interface Design Rules` (96-117): covered by `M4`, `M10`, `N4`, and `N7`.
- `Strategic Programming over Tactical Programming` (118-134): covered by `M5`, `M11`, and `N5`.
- `General-Purpose vs Special-Purpose Modules` (135-143): covered by `M5` and `N5`.
- `Error Handling and Exception Elimination` (144-158): covered by `M4` and `M10`.
- `Pull Complexity Downward` (159-169): covered by `M3`, `M12`, `N3`, and `N8`.
- `Comment Rules` (170-188): covered by `M8`.
- `Function and Variable Rules` (189-203): covered by `M7` and `M13`.
- `Temporal Decomposition Rules` (204-217): covered by `M6`, `M12`, `N8`.
- `Special-General Decomposition` (218-230): covered by `M4`, `M10`, `M11`, `N4`, and `N7`.
- `Review Rules` (231-246): covered by `M1`-`M8`; collapsed into trigger rules and checklist.
- `Forbidden Patterns` (247-266): covered by `M2`, `M5`, `M6`, `M9`, `M11`, `M12`, `N2`, `N5`, `N6`, and `N8`.
- `Code Generation Rules` (267-285): covered by `M1`-`M7`; standalone prose is intentionally lost.
- `Testing Rules` (286-294): covered by `M1`, `M5`, and `M12`; collapsed into trigger rules and checklist.
- `Review Checklist` (295-310): covered by `M1`, `M3`, `M4`, and `M5`; collapsed into the final checklist.
- `Final Instruction` (311-320): covered by `M1`, `M3`, `M4`, and `N1`.
