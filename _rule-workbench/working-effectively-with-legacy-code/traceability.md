# Working Effectively with Legacy Code Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Dropped from `nano.md` as secondary: some detailed technique descriptions and review/test phrasing that support, but do not define, the main legacy strategy.
- Kept whenever a rule changes the first move, safety-net choice, seam creation, dependency-breaking strategy, or risky-area handling.
- Merged the technique catalog and risky-area subsections into a smaller legacy-change discipline with triggers.

## Min mapping

- `M1` Define the problem as safe change; do not start with rewrite or cleanup aesthetics. Source: `Purpose` (3-19), `Primary Directive` (20-38), `Forbidden Patterns / Rewrite as the First Move` (248-252).
- `M2` Get characterization tests or equivalent observations before changing uncertain behavior. Source: `Non-Negotiable Rules` (39-60), `Default Workflow for Legacy Changes` (61-75), `Testing Strategy Rules / Characterization Tests` (78-84).
- `M3` Find or create seams so behavior can be observed and changed without editing everything at once. Source: `Seam Rules` (98-121), `Dependency Breaking Rules` (122-157).
- `M4` Prefer sprout, wrap, and extract-and-override techniques over invasive rewrites when the code is hard to control directly. Source: `Preferred Legacy Techniques` (158-187).
- `M5` Handle risky areas with specific moves for globals, databases, UI/framework code, constructors, and large methods. Source: `Handling Risky Areas` (200-230), `Legacy Refactoring Heuristics` (188-199).
- `M6` Reject no-safety changes, hidden dependency expansion, and cosmetic-only cleanup that leaves the risky structure intact. Source: `Forbidden Patterns` (246-267).

## Nano mapping

- `N1` The first goal is safe change, not rewrite or beauty. Source: `Primary Directive` (20-38), `Rewrite as the First Move` (248-252).
- `N2` Get characterization tests or equivalent observations before changing uncertain behavior. Source: `Non-Negotiable Rules` (39-60), `Characterization Tests` (78-84).
- `N3` Find or create seams and break dependencies explicitly. Source: `Seam Rules` (98-121), `Dependency Breaking Rules` (122-157).
- `N4` Prefer sprout, wrap, or similar isolating techniques over invasive rewrites. Source: `Preferred Legacy Techniques` (158-187).
- `N5` Do not expand hidden dependencies or perform no-safety changes. Source: `Forbidden Patterns` (246-267).

## Intentional omissions

- Detailed technique-by-technique narration: compressed into one rule plus triggers.
- `Testing Rules` (295-304) and `Review Checklist` (305-321): collapsed into triggers and checklist.
