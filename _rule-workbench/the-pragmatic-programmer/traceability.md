# The Pragmatic Programmer Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Re-run under the generalized `PROCESS.md` on 2026-04-26 after adding `Process vs Book Diagnosis`.
- This rerun found no new process bug and no new book-specific miss; current `min.md` and `nano.md` already preserve the book thesis plus repeated local implementation decisions.
- `min.md` and `nano.md` stayed unchanged on this rerun.
- Some broad review wording, estimation detail, and explanatory prose stay compressed because the pragmatic pressure already survives through ownership, DRY, orthogonality, prototypes, automation, feedback loops, and explicit contracts.

## Min mapping

Decision rules:

- `M1` Own the result, think beyond the local edit, and surface trade-offs instead of hiding behind tooling or style ritual. Source: `Core Pragmatic Principles` (36-54), especially `Own the Result` (38-42) and `Think Beyond the Local Edit` (43-47).
- `M2` Treat DRY as one authoritative place per piece of knowledge, not mere text deduplication. Source: `DRY Rules` (55-72), `Forbidden Patterns / Knowledge Duplication` (233-236).
- `M3` Preserve orthogonality so changes stay local and decisions do not fan out across unrelated parts. Source: `Orthogonality Rules` (73-86), `Forbidden Patterns / Non-Orthogonal Design` (237-240).
- `M4` Prefer thin end-to-end tracer bullets over piles of isolated pieces and validate the path early. Source: `Tracer Bullets and Iterative Delivery` (87-100).
- `M5` Use prototypes intentionally to learn quickly, but do not fossilize prototypes or architecture guesses into production design. Source: `Prototyping Rules` (101-109), `Forbidden Patterns / Prototype Fossilization` (245-248).
- `M6` Automate repetitive, error-prone work and make build, test, release, setup, and validation reproducible. Source: `Automation Rules` (110-123), `Tooling Rules` (194-200), `Forbidden Patterns / Manual Everything` (241-244).
- `M7` Shorten feedback loops with cheap early failure signals through tests, types, linters, and scripts. Source: `Feedback Loop Rules` (124-133).
- `M8` Make contracts and assumptions explicit and distinguish programmer errors, contract violations, and expected domain failures. Source: `Design by Contract and Assertions` (134-147), `Error Handling and Recovery` (148-156), `Naming and Communication Rules` (157-166).
- `M9` Favor inspectable text, configs, and scripts where longevity, integration, or automation matter. Source: `Text and Data Rules` (167-173).
- `M10` Treat shared mutable state and async complexity as costs that must earn themselves. Source: `State and Concurrency Rules` (176-183).
- `M11` Apply the broken windows rule: leave touched code, tooling, or docs slightly better than before. Source: `Broken Windows Rule` (203-211).

Trigger rules:

- `M12` When the same rule appears in multiple layers or files, choose one owner and derive the rest. Source: `DRY Rules` (55-72), `Forbidden Patterns / Knowledge Duplication` (233-236).
- `M13` When a change requires edits in many unrelated places, look for missing orthogonality or a hidden shared concern. Source: `Orthogonality Rules` (73-86), `Forbidden Patterns / Non-Orthogonal Design` (237-240).
- `M14` When repeated manual steps or environment rituals appear, automate them before they become tribal knowledge. Source: `Automation Rules` (110-123), `Forbidden Patterns / Manual Everything` (241-244).
- `M15` When a prototype, script, or integration shortcut starts leaking into durable code, either harden it deliberately or replace it. Source: `Prototyping Rules` (101-109), `Forbidden Patterns / Prototype Fossilization` (245-248).
- `M16` When hidden assumptions live only in comments or caller folklore, move them into code, contracts, or automation. Source: `Design by Contract and Assertions` (134-147), `Naming and Communication Rules` (157-166), `Tooling Rules` (194-200).

Final checklist:

- The checklist restates `M2`, `M3`, `M6`, `M7`, and `M11` as a final scan rather than introducing new rules.

## Nano mapping

Decision rules:

- `N1` Own the result beyond the local edit. Source: `Core Pragmatic Principles` (36-54).
- `N2` DRY means one authoritative place per piece of knowledge. Source: `DRY Rules` (55-72).
- `N3` Preserve orthogonality so changes stay local. Source: `Orthogonality Rules` (73-86).
- `N4` Use tracer bullets and prototypes to learn quickly, but do not fossilize them. Source: `Tracer Bullets and Iterative Delivery` (87-100), `Prototyping Rules` (101-109), `Forbidden Patterns / Prototype Fossilization` (245-248).
- `N5` Automate repeatable work and shorten feedback loops. Source: `Automation Rules` (110-123), `Feedback Loop Rules` (124-133).
- `N6` Make important assumptions explicit and leave touched code slightly better than before. Source: `Design by Contract and Assertions` (134-147), `Broken Windows Rule` (203-211).

Trigger rules:

- `N7` When knowledge is copied, choose one owner. Source: `DRY Rules` (55-72).
- `N8` When changes fan out widely, look for missing orthogonality. Source: `Orthogonality Rules` (73-86).
- `N9` When manual steps or hidden assumptions repeat, automate them or encode them explicitly. Source: `Automation Rules` (110-123), `Design by Contract and Assertions` (134-147), `Tooling Rules` (194-200).

Final checklist:

- The checklist restates `N2`, `N3`, `N5`, and `N6` as a final scan rather than introducing new rules.

## Section coverage review

- `Purpose` (3-20): framing merged into `When to use`, `Primary bias to correct`, and `M1`.
- `Primary Directive` (21-35): covered by `M1`, `M3`, `M7`, and `M11`.
- `Core Pragmatic Principles` (36-54): covered by `M1` and `N1`.
- `DRY Rules` (55-72): covered by `M2`, `M12`, `N2`, and `N7`.
- `Orthogonality Rules` (73-86): covered by `M3`, `M13`, `N3`, and `N8`.
- `Tracer Bullets and Iterative Delivery` (87-100): covered by `M4` and `N4`.
- `Prototyping Rules` (101-109): covered by `M5`, `M15`, and `N4`.
- `Automation Rules` (110-123): covered by `M6`, `M14`, `N5`, and `N9`.
- `Feedback Loop Rules` (124-133): covered by `M7` and `N5`.
- `Design by Contract and Assertions` (134-147): covered by `M8`, `M16`, `N6`, and `N9`.
- `Error Handling and Recovery` (148-156): covered by `M8`.
- `Naming and Communication Rules` (157-166): covered by `M8` and `M16`.
- `Text and Data Rules` (167-173): covered by `M9`.
- `State and Concurrency Rules` (176-183): covered by `M10`.
- `Estimation and Increment Rules` (185-193): partly covered by `M4` and `M7`; detailed estimation advice is intentionally lost.
- `Tooling Rules` (194-200): covered by `M6`, `M16`, and `N9`.
- `Broken Windows Rule` (203-211): covered by `M11` and `N6`.
- `Review Rules` (212-226): covered by `M1`-`M11`; collapsed into trigger rules and checklist.
- `Forbidden Patterns` (227-249): covered by `M2`, `M3`, `M5`, `M6`, `M12`, `M13`, `M14`, `M15`, `N2`, `N3`, `N4`, `N7`, and `N8`.
- `Code Generation Rules` (250-268): covered by `M1`-`M10`; standalone prose is intentionally lost.
- `Testing Rules` (269-277): covered by `M6`, `M7`, and `N5`; collapsed into trigger rules and checklist.
- `Review Checklist` (278-293): covered by `M2`, `M3`, `M7`, and `M11`; collapsed into the final checklist.
- `Final Instruction` (294-303): covered by `M1`, `M3`, `M7`, and `M11`.
