# A Philosophy of Software Design Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Dropped from `minimal.md` as default or low-yield: most generic comment, testing, review, and codegen hygiene.
- Kept whenever a rule changes decomposition, interface, information-hiding, or tactical-vs-strategic decisions.
- Merged repeated warnings about shallow code, special cases, and complexity spread into fewer stronger rules.

## Optimal mapping

- `O1` Complexity is the governing metric; reject line-count and cleverness as proxies. Source: `Purpose` (3-19), `Primary Directive` (21-34), `Core Complexity Rules` (36-56).
- `O2` Prefer deep modules and reject pass-through layers. Source: `Module Depth Rules` (57-80), `Forbidden Patterns / Shallow Decomposition` (247-252).
- `O3` Hide volatile details, data representation, and bookkeeping; pull complexity downward. Source: `Information Hiding Rules` (81-95), `Pull Complexity Downward` (159-169), `Forbidden Patterns / Interface Leakage` (253-256).
- `O4` Design narrow semantic interfaces; avoid call-order traps, flags, and mechanism-shaped APIs. Source: `Interface Design Rules` (96-117), `Special-General Decomposition` (218-230).
- `O5` Solve awkwardness strategically, not with local tactical patches or proliferating special cases. Source: `Strategic Programming over Tactical Programming` (118-134), `General-Purpose vs Special-Purpose Modules` (135-143), `Forbidden Patterns / Tactical Complexity Debt` (257-260).
- `O6` Make time/order dependencies explicit and minimize temporal coupling. Source: `Temporal Decomposition Rules` (204-217), `Forbidden Patterns / Complexity Spread` (261-266).
- `O7` Use comments only for contracts, invariants, or rationale that code cannot express. Source: `Comment Rules` (170-188).

## Minimal mapping

- `M1` Optimize for lower cognitive load, not fewer lines. Source: `Primary Directive` (21-34), `Core Complexity Rules` (36-56).
- `M2` Prefer deep modules and reject wrappers that do not hide real complexity. Source: `Module Depth Rules` (57-80), `Forbidden Patterns / Shallow Decomposition` (247-252).
- `M3` Hide volatile details and pull messy edge conditions below stable interfaces. Source: `Information Hiding Rules` (81-95), `Pull Complexity Downward` (159-169).
- `M4` Keep interfaces narrow and semantic; avoid staged APIs, booleans, and mechanism leakage. Source: `Interface Design Rules` (96-117), `Special-General Decomposition` (218-230).
- `M5` When a change feels awkward, fix the design instead of layering tactical special cases. Source: `Strategic Programming over Tactical Programming` (118-134), `General-Purpose vs Special-Purpose Modules` (135-143).

## Intentional omissions

- `Function and Variable Rules` (189-203): largely default coding hygiene unless they affect complexity directly.
- `Testing Rules` (286-294) and `Review Checklist` (295-310): collapsed into trigger rules and final checklist.
- `Code Generation Rules` (267-285): merged into operational rules above.
