# Refactoring Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Re-run under the generalized `PROCESS.md` on 2026-04-26 after adding `Process vs Book Diagnosis`.
- This rerun found no new process bug and no new book-specific miss; existing `min.md` and `nano.md` already preserve the book thesis and repeated micro-decisions.
- `min.md` and `nano.md` stayed unchanged on this rerun.
- The long smell taxonomy and move catalog stay compressed because the core refactoring pressure already survives through behavior preservation, small verified steps, safety nets, and stopping discipline.

## Min mapping

Decision rules:

- `M1` Refactoring preserves observable behavior and stays distinct from feature work where practical. Source: `Purpose` (3-19), `Primary Directive` (20-34), `What Counts as Refactoring` (35-52).
- `M2` Use small, verifiable steps and reject big-bang rewrites or mixed-intent patches. Source: `Non-Negotiable Rules` (53-78), `Forbidden Patterns / Big-Bang Rewrite` (266-270), `Forbidden Patterns / Mixed-Intent Patches` (271-275).
- `M3` Get a safety net first: tests, characterization, assertions, or another credible verification path. Source: `Safety Rules` (79-103), especially `Tests and Verification` (81-87).
- `M4` Refactor toward the smell that blocks change now: duplication, long functions, hidden dependencies, shotgun surgery, primitive obsession, sprawling conditionals, or speculative abstraction. Source: `Code Smell Policy` (104-157).
- `M5` Prefer known moves such as rename, extract, move, inline, simplify, split phase, and data-shape improvements over improvised structural leaps. Source: `Preferred Refactoring Moves` (158-190), `Function-Level Rules` (191-202), `Class and Module Rules` (203-213), `Rules for Working with Conditionals` (214-223), `Data and Mutation Rules` (224-233), `Error Handling Rules` (234-242).
- `M6` Make preparatory refactors only when they directly lower the risk of the requested change. Source: `Safety Rules / Preparatory Refactoring` (94-103), `Code Generation Rules` (293-320).
- `M7` Stop when the requested change is safe and clear; do not refactor theatrically or abstract too early. Source: `Stopping Rules` (332-342), `Forbidden Patterns / Abstracting Too Early` (276-280), `Forbidden Patterns / Refactoring Theater` (281-285).

Trigger rules:

- `M8` When a patch mixes behavior change and structural cleanup, split the intent unless context makes that impossible. Source: `Primary Directive` (20-34), `Forbidden Patterns / Mixed-Intent Patches` (271-275).
- `M9` When a risky area lacks tests, characterize current behavior before major structural edits. Source: `Safety Rules` (79-103), `Forbidden Patterns / Untested Structural Surgery` (286-292).
- `M10` When a conditional tree keeps growing, consider extraction, split phase, polymorphism, or data-driven structure. Source: `Code Smell Policy / Switch Statements and Conditionals` (144-147), `Rules for Working with Conditionals` (214-223).
- `M11` When the urge is to rewrite, first ask what smaller transformation would recover control. Source: `Non-Negotiable Rules` (53-78), `Forbidden Patterns / Big-Bang Rewrite` (266-270).

Final checklist:

- The checklist restates `M1`, `M2`, `M4`, and `M7` as a final scan rather than introducing new rules.

## Nano mapping

Decision rules:

- `N1` Refactoring preserves observable behavior. Source: `What Counts as Refactoring` (35-52).
- `N2` Use small, verifiable steps and no big-bang rewrites. Source: `Non-Negotiable Rules` (53-78), `Forbidden Patterns / Big-Bang Rewrite` (266-270).
- `N3` Get a safety net first. Source: `Safety Rules` (79-103).
- `N4` Refactor the smell that blocks change now, not every smell in sight. Source: `Code Smell Policy` (104-157), `Stopping Rules` (332-342).
- `N5` Keep refactoring and behavior change distinct when practical. Source: `Primary Directive` (20-34), `Forbidden Patterns / Mixed-Intent Patches` (271-275).

Trigger rules:

- `N6` When a patch mixes intents, split it. Source: `Forbidden Patterns / Mixed-Intent Patches` (271-275).
- `N7` When structure is risky and untested, characterize first. Source: `Safety Rules` (79-103), `Forbidden Patterns / Untested Structural Surgery` (286-292).
- `N8` When tempted to rewrite, find the next smaller safe move. Source: `Non-Negotiable Rules` (53-78), `Forbidden Patterns / Big-Bang Rewrite` (266-270).

Final checklist:

- The checklist restates `N1`, `N2`, and `N3` as a final scan rather than introducing new rules.

## Section coverage review

- `Purpose` (3-19): covered by `M1`.
- `Primary Directive` (20-34): covered by `M1`, `M8`, and `N5`.
- `What Counts as Refactoring` (35-52): covered by `M1` and `N1`.
- `Non-Negotiable Rules` (53-78): covered by `M2`, `M11`, `N2`, and `N8`.
- `Safety Rules` (79-103): covered by `M3`, `M6`, `M9`, `N3`, and `N7`.
- `Code Smell Policy` (104-157): covered by `M4`, `M10`, and `N4`.
- `Preferred Refactoring Moves` (158-190): covered by `M5`.
- `Function-Level Rules` (191-202): covered by `M5`.
- `Class and Module Rules` (203-213): covered by `M5`.
- `Rules for Working with Conditionals` (214-223): covered by `M5` and `M10`.
- `Data and Mutation Rules` (224-233): covered by `M5`.
- `Error Handling Rules` (234-242): covered by `M5`.
- `Review Rules` (243-261): covered by `M2`, `M3`, `M4`, and `M7`; collapsed into trigger rules and checklist.
- `Forbidden Patterns` (262-292): covered by `M2`, `M7`, `M8`, `M9`, `M11`, `N2`, `N5`, `N6`, `N7`, and `N8`.
- `Code Generation Rules` (293-320): covered by `M2`, `M5`, and `M6`.
- `Testing Rules` (321-331): covered by `M3`, `M9`, `N3`, and `N7`; collapsed into trigger rules and checklist.
- `Stopping Rules` (332-342): covered by `M7` and `N4`.
- `Review Checklist` (343-361): covered by `M1`, `M2`, `M4`, and `M7`; collapsed into the final checklist.
- `Final Instruction` (362-366): covered by `M1`, `M2`, `M3`, and `M7`.
