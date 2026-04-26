# Refactoring Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Dropped from `minimal.md` as secondary: detailed smell taxonomy and some movement-specific nomenclature.
- Kept whenever a rule changes safety, patch shape, smell response, or stopping behavior.
- Merged the long smell list and preferred-move list into a smaller operational refactoring discipline.

## Optimal mapping

- `O1` Refactoring preserves observable behavior and stays distinct from feature work where practical. Source: `Purpose` (3-19), `Primary Directive` (20-34), `What Counts as Refactoring` (35-52).
- `O2` Use small, verifiable steps; reject big-bang rewrites and mixed-intent patches. Source: `Non-Negotiable Rules` (53-78), `Forbidden Patterns / Big-Bang Rewrite` (266-270), `Forbidden Patterns / Mixed-Intent Patches` (271-275).
- `O3` Get a safety net first: tests, characterization, assertions, or another credible verification path. Source: `Safety Rules` (79-103), especially `Tests and Verification` (81-87).
- `O4` Refactor toward the smell that blocks change now: duplication, long functions, hidden dependencies, shotgun surgery, primitive obsession, conditionals, speculative generality. Source: `Code Smell Policy` (104-157).
- `O5` Prefer known moves such as rename, extract, move, inline, simplify, split phase, and data-shape improvements over improvised structural leaps. Source: `Preferred Refactoring Moves` (158-190), `Function-Level Rules` (191-202), `Class and Module Rules` (203-213).
- `O6` Stop when the requested change is safe and clear; do not refactor theatrically or abstract too early. Source: `Stopping Rules` (332-342), `Forbidden Patterns / Abstracting Too Early` (276-280), `Forbidden Patterns / Refactoring Theater` (281-285).

## Minimal mapping

- `M1` Refactoring preserves observable behavior. Source: `What Counts as Refactoring` (35-52).
- `M2` Use small, verifiable steps; no big-bang rewrites. Source: `Non-Negotiable Rules` (53-78), `Forbidden Patterns / Big-Bang Rewrite` (266-270).
- `M3` Get a safety net first. Source: `Safety Rules` (79-103).
- `M4` Refactor the smell that blocks change now, not every smell in sight. Source: `Code Smell Policy` (104-157), `Stopping Rules` (332-342).
- `M5` Keep refactoring and behavior change distinct when practical. Source: `Primary Directive` (20-34), `Forbidden Patterns / Mixed-Intent Patches` (271-275).

## Intentional omissions

- Detailed per-smell and per-move terminology: preserved as one operational smell rule and one preferred-moves rule.
- `Testing Rules` (321-331) and `Review Checklist` (343-361): collapsed into triggers and checklist.
