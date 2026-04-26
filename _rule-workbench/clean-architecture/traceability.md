# Clean Architecture Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Re-run under the generalized `PROCESS.md` on 2026-04-26 after adding `Process vs Book Diagnosis`.
- This rerun identified book-specific misses, not a new process bug: the source explicitly treats inner ownership of ports and role-based naming as operational Clean Architecture pressure.
- `min.md` was strengthened to keep entity and invariant placement explicit, to preserve inner ownership of ports, and to preserve role-based naming and anti-god-service pressure as repeated micro-decisions.
- `nano.md` stayed unchanged because the new misses belong in on-demand pressure, not in the always-on budget.
- Detailed naming examples, output-shape prose, and repeated checklist wording stay compressed unless they change a concrete architectural decision.

## Min mapping

Decision rules:

- `M1` Enforce the dependency rule: source dependencies point toward policy, never toward frameworks or delivery mechanisms. Source: `Non-Negotiable Rules` (19-25, 66-70), `Architecture Heuristics / Dependency Direction` (215-223), `Forbidden Patterns / Direction Violations` (333-337).
- `M2` Keep the domain pure and put core invariants in entities or domain objects, not in controllers, jobs, repository code, or SQL. Source: `Non-Negotiable Rules` (26-29, 61-64), `Required Layer Responsibilities / Domain Layer` (76-96), `Forbidden Patterns / Database Leakage` (313-316), `Forbidden Patterns / Controller-Centric Logic` (318-321), `Refactoring Rules` (349-360).
- `M3` Let the application layer coordinate use cases, transactions, and ports without becoming a dumping ground for policy. Source: `Non-Negotiable Rules` (56-59), `Required Layer Responsibilities / Application Layer` (97-115), `Architecture Heuristics / Policy vs Detail` (224-231).
- `M4` Keep adapters responsible for translation between external formats and internal models. Source: `Non-Negotiable Rules` (41-49), `Required Layer Responsibilities / Interface Adapters Layer` (116-133), `Code Generation Rules / Use Plain Models at Boundaries` (177-181).
- `M5` Treat infrastructure as replaceable detail, keep ports owned by inner layers and implemented outward, and keep wiring at the composition root. Source: `Required Layer Responsibilities / Infrastructure Layer` (134-153), `Code Generation Rules / Create Ports for Volatile Dependencies` (182-195), `Code Generation Rules / Keep Wiring in the Main Component` (196-200), `Code Generation Rules / Prefer Stable Dependencies` (201-204), `Architecture Heuristics / Stable Core, Replaceable Edge` (233-242), `Preferred Default Shapes / Preferred dependency pattern` (443-447).
- `M6` Define the use case and its plain boundary models before wiring details. Source: `Code Generation Rules / Define the Use Case First` (160-176), `Code Generation Rules / Use Plain Models at Boundaries` (177-181), `Code Generation Rules / Keep Boundaries Visible` (206-209), `Preferred Default Shapes / Preferred use case shape` (436-441).
- `M7` Prefer feature-oriented structure and role-based names so use-case ownership stays visible instead of dissolving into controller/service/repository buckets or generic escape hatches. Source: `Non-Negotiable Rules / Organize by Use Case` (51-55), `Architecture Heuristics / Feature First Structure` (244-257), `Naming Rules` (261-269), `Forbidden Patterns / Utility Dumping Grounds` (338-341), `Preferred Default Shapes / Preferred feature shape` (424-435).
- `M8` Test the core without real infrastructure and add focused adapter tests where translation or integration behavior is the risk. Source: `Testing Rules / Core Tests First` (274-286), `Testing Rules / Adapter Tests` (287-295), `Testing Rules / Test Through Supported Boundaries` (297-300).

Trigger rules:

- `M9` When framework or ORM types appear in domain or use-case code, stop and move translation to an adapter. Source: `Non-Negotiable Rules` (31-45), `Code Generation Rules / Use Plain Models at Boundaries` (177-181), `Forbidden Patterns / Framework Leakage` (308-312).
- `M10` When a controller, handler, job, repository, or SQL path starts carrying business rules or invariant checks, move policy inward. Source: `Non-Negotiable Rules` (56-64), `Forbidden Patterns / Database Leakage` (313-316), `Forbidden Patterns / Controller-Centric Logic` (318-321), `Refactoring Rules` (349-360).
- `M11` When adding a new external dependency, introduce a port if the core would otherwise learn vendor or transport details. Source: `Non-Negotiable Rules` (46-49), `Code Generation Rules / Create Ports for Volatile Dependencies` (182-195), `Code Generation Rules / Keep Boundaries Visible` (206-209).
- `M12` When a cross-layer shortcut appears or a large `*Service` starts spanning multiple actions, split by use case and restore the boundary. Source: `Non-Negotiable Rules` (51-59, 66-70), `Forbidden Patterns / God Services` (323-326), `Forbidden Patterns / Layer Bypass` (328-331), `Forbidden Patterns / Utility Dumping Grounds` (338-341), `Refactoring Rules` (362-371).

Final checklist:

- The checklist restates `M1`, `M2`, `M5`, `M6`, and `M8` as a final scan rather than introducing new rules.

## Nano mapping

Decision rules:

- `N1` Business rules must not depend on frameworks, databases, UI, or vendor SDKs. Source: `Non-Negotiable Rules` (19-45), `Architecture Heuristics / Dependency Direction` (215-223).
- `N2` Domain owns policy and invariants, application orchestrates use cases, adapters translate, and infrastructure implements details. Source: `Non-Negotiable Rules` (56-64), `Required Layer Responsibilities` (74-153).
- `N3` Define the use case and plain boundary models before wiring external details. Source: `Code Generation Rules / Define the Use Case First` (160-181), `Preferred Default Shapes / Preferred use case shape` (436-441).
- `N4` Put volatile dependencies behind ports and keep composition at the edge. Source: `Non-Negotiable Rules` (46-49), `Code Generation Rules` (182-209), `Preferred Default Shapes / Preferred dependency pattern` (443-447).
- `N5` Prefer feature and use-case structure over controller/service/repository buckets. Source: `Non-Negotiable Rules / Organize by Use Case` (51-55), `Architecture Heuristics / Feature First Structure` (244-257), `Preferred Default Shapes / Preferred feature shape` (424-435).
- `N6` Test the core independently and test adapters at real boundaries. Source: `Testing Rules` (272-300).

Trigger rules:

- `N7` When framework or ORM types enter core code, move translation outward. Source: `Non-Negotiable Rules` (31-45), `Forbidden Patterns / Framework Leakage` (308-312).
- `N8` When a controller, job, repository, or god service grows business rules, move them inward and split by use case. Source: `Non-Negotiable Rules` (56-64), `Forbidden Patterns / Controller-Centric Logic` (318-321), `Forbidden Patterns / God Services` (323-326), `Refactoring Rules` (349-365).
- `N9` When a new dependency or shortcut would couple the core to a vendor or bypass the intended path, add a port and restore the boundary. Source: `Non-Negotiable Rules` (46-49, 66-70), `Code Generation Rules` (182-209), `Forbidden Patterns / Layer Bypass` (328-341), `When Tradeoffs Are Necessary` (450-456).

Final checklist:

- The checklist restates `N1`, `N2`, `N3`, `N4`, and `N5` as a final scan rather than introducing new rules.

## Section coverage review

- `Purpose` (3-15): framing merged into the `When to use`, `Primary bias to correct`, and `M1`/`N1`.
- `Non-Negotiable Rules` (19-71): covered by `M1`-`M7`, `M9`-`M12`, and `N1`-`N5`, `N7`-`N9`.
- `Required Layer Responsibilities / Domain Layer` (76-96): covered by `M2` and `N2`.
- `Required Layer Responsibilities / Application Layer` (97-115): covered by `M3` and `N2`.
- `Required Layer Responsibilities / Interface Adapters Layer` (116-133): covered by `M4` and `N2`.
- `Required Layer Responsibilities / Infrastructure Layer` (134-153): covered by `M5` and `N2`.
- `Code Generation Rules / Define the Use Case First` (160-176): covered by `M6` and `N3`.
- `Code Generation Rules / Use Plain Models at Boundaries` (177-181): covered by `M4`, `M6`, `M9`, `N3`, and `N7`.
- `Code Generation Rules / Create Ports for Volatile Dependencies` (182-195): covered by `M5`, `M11`, `N4`, and `N9`.
- `Code Generation Rules / Keep Wiring in the Main Component` (196-200): covered by `M5` and `N4`.
- `Code Generation Rules / Prefer Stable Dependencies` (201-204): covered by `M1`, `M5`, `N1`, and `N4`.
- `Code Generation Rules / Keep Boundaries Visible` (206-209): covered by `M6`, `M11`, `N3`, and `N9`.
- `Architecture Heuristics / Dependency Direction` (215-223): covered by `M1` and `N1`.
- `Architecture Heuristics / Policy vs Detail` (224-231): covered by `M3`, `M4`, `M5`, and `N2`.
- `Architecture Heuristics / Stable Core, Replaceable Edge` (233-242): covered by `M5` and `N4`.
- `Architecture Heuristics / Feature First Structure` (244-257): covered by `M7` and `N5`.
- `Naming Rules` (261-269): covered by `M7`; the full list of examples is compressed, but the anti-`*Service`/`Helper`/`Manager` pressure is retained.
- `Testing Rules / Core Tests First` (274-286): covered by `M8` and `N6`.
- `Testing Rules / Adapter Tests` (287-295): covered by `M8` and `N6`.
- `Testing Rules / Test Through Supported Boundaries` (297-300): covered by `M8` and `N6`.
- `Forbidden Patterns / Framework Leakage` (308-312): covered by `M9` and `N7`.
- `Forbidden Patterns / Database Leakage` (313-316): covered by `M2`, `M10`, and `N8`.
- `Forbidden Patterns / Controller-Centric Logic` (318-321): covered by `M10` and `N8`.
- `Forbidden Patterns / God Services` (323-326): covered by `M12` and `N8`.
- `Forbidden Patterns / Layer Bypass` (328-331): covered by `M12` and `N9`.
- `Forbidden Patterns / Direction Violations` (333-337): covered by `M1` and `N1`.
- `Forbidden Patterns / Utility Dumping Grounds` (338-341): covered by `M7`, `M12`, `N5`, and `N9`.
- `Refactoring Rules` (345-371): covered by `M2`, `M4`, `M8`, `M10`, `M11`, `M12`, `N6`, `N8`, and `N9`.
- `Output Expectations` (375-398): implementation shape is covered by `M5`, `M6`, and `M7`; review prompts are covered by `M9`-`M12`; standalone prose is intentionally lost.
- `Review Checklist` (400-418): covered by `M1`-`M8` and `N1`-`N6`; collapsed into the final checklists.
- `Preferred Default Shapes / Preferred feature shape` (424-435): covered by `M7` and `N5`.
- `Preferred Default Shapes / Preferred use case shape` (436-441): covered by `M6` and `N3`.
- `Preferred Default Shapes / Preferred dependency pattern` (443-447): covered by `M1`, `M5`, and `N4`.
- `When Tradeoffs Are Necessary` (450-458): covered by `M11`, `M12`, and `N9`.
- `Final Instruction` (462-471): covered by `M1`, `M5`, `M8`, `N1`, `N4`, and `N6`.
