# Clean Code Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Re-run under the generalized `PROCESS.md` on 2026-04-26 after adding `Process vs Book Diagnosis`.
- This rerun identified book-specific misses, not a new process bug: the source explicitly treats validation discipline and anti-scope-broadening as operational Clean Code rules, not mere reporting preferences.
- `min.md` was strengthened to keep invalid-state handling explicit, to preserve async/concurrency discipline as a trigger, and to retain proportionate validation plus anti-scope-broadening pressure.
- `nano.md` stayed unchanged because these additional rules belong in the stronger on-demand layer rather than the always-on budget.
- Detailed formatting mechanics, output-reporting prose, and repeated review wording stay compressed unless they change a repeated coding decision.

## Min mapping

Decision rules:

- `M1` Write for local reasoning so a reader can follow the path without reconstructing hidden state, wide jumps, or trivia. Source: `Core clean code principles` (14-23), `Formatting and structure` (81-91), `Change workflow` (191-202).
- `M2` Use precise names and one term per concept; rename when vocabulary hides intent or overloads meaning. Source: `Naming rules` (24-43), `Review checklist` (215-229), `Hard rules` (241-241).
- `M3` Keep functions small, focused, top-down, and at one abstraction level. Source: `Function rules` (46-52, 60-63), `Formatting and structure` (86-91).
- `M4` Keep parameters few and meaningful; avoid boolean flags, output parameters, and grab-bag argument lists. Source: `Function rules` (52-54), `Smells to detect and eliminate` (179-180).
- `M5` Separate commands from queries and eliminate hidden side effects. Source: `Function rules` (55-57), `Hard rules` (244-244).
- `M6` Keep the happy path readable, isolate error handling, invalid-state handling, and cleanup, and prefer explicit optionality or typed results over null-like sentinel flow when the language supports it. Source: `Function rules` (58-59), `Error handling` (115-124).
- `M7` Expose behavior rather than raw representation and avoid train-wreck access, utility dumping grounds, and mixed responsibilities. Source: `Objects, modules, and data structures` (93-103), `Class and module design` (104-110).
- `M8` Make public APIs small, explicit, and hard to misuse, and organize code so likely changes stay local. Source: `Class and module design` (110-114), `Boundaries and external dependencies` (126-133), `Implementation preferences` (206-211).
- `M9` Use comments only for rationale, constraints, warnings, or external contracts; never as a bandage for bad structure. Source: `Comment rules` (64-80).
- `M10` Treat tests as production code and back changes with proportionate validation before calling them done. Source: `Tests` (134-147), `Change workflow` (199-200).
- `M11` When touching code, remove the smell that most increases change cost, but do not silently broaden the task beyond the smallest cleanup that makes the requested change safe. Source: `Priority and behavior` (8-12), `Refactoring rules` (158-168), `Smells to detect and eliminate` (169-190), `Change workflow` (193-202), `Hard rules` (245-246).

Trigger rules:

- `M12` When a function mixes setup, validation, computation, and side effects, split the phases. Source: `Function rules` (47-59, 61-63), `Smells to detect and eliminate` (175-182).
- `M13` When a comment explains control flow, simplify names or structure before keeping the comment. Source: `Comment rules` (66-78).
- `M14` When a function both mutates and answers, or hides a mode switch behind a flag, separate the responsibilities. Source: `Function rules` (53-57), `Hard rules` (244-244).
- `M15` When async or concurrency enters, minimize shared mutable state and make cancellation, timeouts, and cleanup explicit. Source: `Concurrency and async work` (148-156), `Error handling` (124-124).
- `M16` When a boundary leaks framework, vendor, or persistence quirks inward, add or strengthen a local adapter. Source: `Boundaries and external dependencies` (126-133), `Objects, modules, and data structures` (101-103).
- `M17` When fixing a bug or changing behavior, add or update the test that protects the intended contract. Source: `Tests` (144-146), `Change workflow` (199-200).
- `M18` When cleanup starts spreading into unrelated areas, cut back to the smallest refactor that keeps the requested change safe and readable. Source: `Change workflow` (195-198), `Hard rules` (245-246).

Final checklist:

- The checklist restates `M1`, `M2`, `M5`, `M8`, `M10`, and `M11` as a final scan rather than introducing new rules.

## Nano mapping

Decision rules:

- `N1` Write for local reasoning and use precise names with one term per concept. Source: `Core clean code principles` (14-23), `Naming rules` (24-43).
- `N2` Split boolean flags, mixed abstraction levels, and hidden side effects out of functions. Source: `Function rules` (49-55, 61-63), `Smells to detect and eliminate` (177-180).
- `N3` Separate commands from queries and keep parameters small and meaningful. Source: `Function rules` (52-57).
- `N4` Keep the happy path readable and make invalid states, errors, and cleanup explicit instead of implicit. Source: `Function rules` (58-59), `Error handling` (115-124).
- `N5` Use comments only for rationale or contracts, not to explain confusing code. Source: `Comment rules` (64-80).
- `N6` When touching code, remove the smell most likely to make the next change risky or unclear. Source: `Refactoring rules` (158-168), `Smells to detect and eliminate` (169-190), `Change workflow` (193-202).

Trigger rules:

- `N7` When a function both mutates and answers, split it. Source: `Function rules` (55-57), `Hard rules` (244-244).
- `N8` When a comment explains the flow, simplify the code first. Source: `Comment rules` (66-78).
- `N9` When async, concurrency, or framework quirks spread the change, reduce shared mutable state and add the right boundary instead of more branching. Source: `Concurrency and async work` (148-156), `Boundaries and external dependencies` (126-133), `Smells to detect and eliminate` (189-189).

Final checklist:

- The checklist restates `N1`, `N2`, `N3`, and `N6` as a final scan rather than introducing new rules.

## Section coverage review

- `Priority and behavior` (5-12): safe-change, long-term complexity, and Boy Scout pressure are covered by `M11` and `N6`; assistant-facing priority prose is intentionally lost as standalone text.
- `Core clean code principles` (14-23): covered by `M1` and `N1`.
- `Naming rules` (24-43): covered by `M2` and `N1`.
- `Function rules` (44-63): covered by `M3`, `M4`, `M5`, `M6`, `M12`, `M14`, `N2`, `N3`, `N4`, and `N7`.
- `Comment rules` (64-80): covered by `M9`, `M13`, `N5`, and `N8`.
- `Formatting and structure` (81-91): local reasoning, top-down story, and scanning pressure are covered by `M1` and `M3`; detailed formatting mechanics are intentionally lost.
- `Objects, modules, and data structures` (93-103): covered by `M7`, `M16`, and `N9`.
- `Class and module design` (104-114): covered by `M7` and `M8`.
- `Error handling` (115-124): covered by `M6`, `M15`, and `N4`.
- `Boundaries and external dependencies` (126-133): covered by `M8`, `M16`, and `N9`.
- `Tests` (134-147): covered by `M10` and `M17`.
- `Concurrency and async work` (148-156): covered by `M15` and `N9`.
- `Refactoring rules` (158-168): covered by `M11` and `N6`.
- `Smells to detect and eliminate` (169-190): covered by `M11`, `M12`, `M14`, `N2`, `N6`, and `N9`.
- `Change workflow` (191-202): covered by `M1`, `M10`, `M11`, `M17`, `M18`, and `N6`.
- `Implementation preferences` (204-214): covered by `M8` and `M11`; the anti-premature-optimization detail is intentionally lost as standalone wording.
- `Review checklist` (215-229): covered by `M1`-`M11` and `N1`-`N6`; collapsed into the final checklists.
- `Output Expectations` (230-238): intentionally lost as standalone prose because it is reporting guidance rather than a primary coding bias; conflict and boundary pressure survive indirectly through `M11` and `M16`.
- `Hard rules` (239-246): covered by `M2`, `M5`, `M9`, `M11`, `M14`, `M18`, `N2`, and `N7`.
