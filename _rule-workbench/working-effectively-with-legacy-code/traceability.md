# Working Effectively with Legacy Code Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Re-run under the generalized `PROCESS.md` on 2026-04-26 after adding `Process vs Book Diagnosis`.
- This rerun found no new process bug and no new book-specific miss; existing `min.md` and `nano.md` already preserve the book thesis and repeated micro-decisions.
- `min.md` and `nano.md` stayed unchanged on this rerun.
- Detailed technique narration and review/test scaffolding stay compressed because the operational legacy-change pressure already survives through safe-change-first, characterization, seams, dependency breaking, and anti-rewrite rules.

## Min mapping

Decision rules:

- `M1` Define the job as making change safe, not as rewriting old code into your preferred shape. Source: `Purpose` (3-19), `Primary Directive` (20-38), `Forbidden Patterns / Rewrite as the First Move` (248-252).
- `M2` Get characterization tests or equivalent observations before changing behavior you do not fully understand. Source: `Non-Negotiable Rules` (39-60), `Default Workflow for Legacy Changes` (61-75), `Testing Strategy Rules / Characterization Tests` (78-84).
- `M3` Find or create seams so you can observe and change behavior without editing the entire dependency tangle at once. Source: `Seam Rules` (98-121), `Dependency Breaking Rules` (122-157).
- `M4` Break dependencies explicitly: hidden inputs, hard outputs, construction problems, globals, and static calls should become visible points of control. Source: `Dependency Breaking Rules` (122-157).
- `M5` Prefer sprout, wrap, and extract-and-override style techniques when direct edits would require too much risky surgery. Source: `Preferred Legacy Techniques` (158-187).
- `M6` Handle risky areas with specific moves for database-heavy code, UI or framework code, constructors, large methods, and global dependencies. Source: `Legacy Refactoring Heuristics` (188-199), `Handling Risky Areas` (200-230).
- `M7` Reject no-safety changes, rewrite-first instincts, and cosmetic cleanup that leaves the dangerous structure untouched. Source: `Forbidden Patterns` (246-267).

Trigger rules:

- `M8` When a method is too large to reason about safely, create a seam before making a semantic change. Source: `Seam Rules` (98-121), `Handling Risky Areas / Large Methods` (202-207).
- `M9` When globals, statics, constructors, or framework callbacks control the flow, break one dependency at a time until the behavior is testable. Source: `Dependency Breaking Rules` (122-157), `Handling Risky Areas` (208-230).
- `M10` When behavior is uncertain, characterize first even if the tests are ugly. Source: `Testing Strategy Rules` (76-97), `Default Workflow for Legacy Changes` (61-75).
- `M11` When the urge is to rewrite, ask what smaller sprout or wrap move would let you change the code safely today. Source: `Preferred Legacy Techniques` (158-187), `Forbidden Patterns / Rewrite as the First Move` (248-252).

Final checklist:

- The checklist restates `M1`, `M2`, `M3`, and `M4` as a final scan rather than introducing new rules.

## Nano mapping

Decision rules:

- `N1` The first goal is safe change, not rewrite or beauty. Source: `Primary Directive` (20-38), `Forbidden Patterns / Rewrite as the First Move` (248-252).
- `N2` Get characterization tests or equivalent observations before changing uncertain behavior. Source: `Non-Negotiable Rules` (39-60), `Testing Strategy Rules / Characterization Tests` (78-84).
- `N3` Find or create seams and break dependencies explicitly. Source: `Seam Rules` (98-121), `Dependency Breaking Rules` (122-157).
- `N4` Prefer sprout, wrap, or similar isolating techniques over invasive rewrites. Source: `Preferred Legacy Techniques` (158-187).
- `N5` Do not expand hidden dependencies or perform no-safety changes. Source: `Forbidden Patterns` (246-267).

Trigger rules:

- `N6` When behavior is uncertain, characterize first. Source: `Testing Strategy Rules` (76-97).
- `N7` When globals, statics, or constructors dominate, break one dependency at a time. Source: `Dependency Breaking Rules` (122-157), `Handling Risky Areas` (208-230).
- `N8` When rewrite feels tempting, look for the next smaller seam. Source: `Preferred Legacy Techniques` (158-187), `Forbidden Patterns / Rewrite as the First Move` (248-252).

Final checklist:

- The checklist restates `N2`, `N3`, and `N5` as a final scan rather than introducing new rules.

## Section coverage review

- `Purpose` (3-19): framing merged into `When to use`, `Primary bias to correct`, and `M1`.
- `Primary Directive` (20-38): covered by `M1` and `N1`.
- `Non-Negotiable Rules` (39-60): covered by `M2` and `N2`.
- `Default Workflow for Legacy Changes` (61-75): covered by `M2` and `M10`.
- `Testing Strategy Rules` (76-97): covered by `M2`, `M10`, `N2`, and `N6`.
- `Seam Rules` (98-121): covered by `M3`, `M8`, and `N3`.
- `Dependency Breaking Rules` (122-157): covered by `M3`, `M4`, `M9`, `N3`, and `N7`.
- `Preferred Legacy Techniques` (158-187): covered by `M5`, `M11`, `N4`, and `N8`.
- `Legacy Refactoring Heuristics` (188-199): covered by `M6`.
- `Handling Risky Areas` (200-230): covered by `M6`, `M8`, `M9`, and `N7`.
- `Review Rules` (231-245): covered by `M1`-`M7`; collapsed into trigger rules and checklist.
- `Forbidden Patterns` (246-267): covered by `M1`, `M7`, `M11`, `N1`, `N5`, and `N8`.
- `Code Generation Rules` (268-294): covered by `M1`-`M6`; standalone prose is intentionally lost.
- `Testing Rules` (295-304): covered by `M2`, `M3`, and `M4`; collapsed into trigger rules and checklist.
- `Review Checklist` (305-321): covered by `M1`, `M2`, `M3`, and `M4`; collapsed into the final checklist.
- `Final Instruction` (322-331): covered by `M1`, `M2`, `M3`, and `M7`.
