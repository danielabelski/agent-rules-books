# Patterns of Enterprise Application Architecture Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Re-run under the generalized `PROCESS.md` on 2026-04-26 after adding `Process vs Book Diagnosis`.
- This rerun found no new process bug and no new book-specific miss; existing `min.md` and `nano.md` already preserve the book thesis and repeated micro-decisions.
- `min.md` and `nano.md` stayed unchanged on this rerun.
- Long pattern catalogs and presentation-layer detail stay compressed because the first-order pressure already survives through business-logic pattern choice, persistence pattern choice, transaction boundaries, and coarse-grained remote design.

## Min mapping

Decision rules:

- `M1` Choose the business-logic pattern deliberately: transaction script for simple workflows, table module for table-centric logic, and domain model for rich invariants and behavior. Source: `Choosing the Business Logic Pattern` (60-96).
- `M2` Use service layer for application workflow and keep controllers thin; use remote facades and DTOs only when crossing expensive or unstable boundaries. Source: `Application Workflow Rules` (97-131), `Distribution Rules` (235-248).
- `M3` Match the persistence pattern to complexity: Active Record is acceptable for simple CRUD, while Data Mapper or Repository fits richer separation needs. Source: `Persistence Pattern Rules` (132-165), `Forbidden Patterns / Generic Repository Everywhere` (296-299), `Forbidden Patterns / ORM-Driven Everything` (300-303).
- `M4` Use Unit of Work, Identity Map, and Lazy Load deliberately and visibly, not as invisible magic that changes consistency or performance expectations. Source: `Identity, Caching, and Unit-of-Work Rules` (166-188).
- `M5` Make transaction boundaries and locking strategy explicit around real contention and consistency needs. Source: `Concurrency and Transaction Rules` (189-209), `Forbidden Patterns / Transaction Chaos` (310-313).
- `M6` Keep integration and distribution coarse-grained and explicit; do not design as if remote calls were cheap local method calls. Source: `Offline and Integration Rules` (221-234), `Distribution Rules` (235-248), `Forbidden Patterns / Distributed Object Fantasy` (307-309).

Trigger rules:

- `M7` When adding a repository, ask whether it hides meaningful complexity or merely restates the ORM. Source: `Persistence Pattern Rules` (132-165), `Forbidden Patterns / Generic Repository Everywhere` (296-299).
- `M8` When a simple use case starts accumulating domain rules, revisit whether transaction script is still enough. Source: `Choosing the Business Logic Pattern` (60-96).
- `M9` When remote calls become chatty, redesign the boundary as a coarse-grained contract. Source: `Application Workflow Rules / Remote Facade` (108-118), `Distribution Rules` (235-248), `Forbidden Patterns / Distributed Object Fantasy` (307-309).
- `M10` When contention or duplicate updates matter, choose an explicit lock or conflict strategy instead of hoping the ORM saves you. Source: `Concurrency and Transaction Rules` (189-209), `Forbidden Patterns / Transaction Chaos` (310-313).

Final checklist:

- The checklist restates `M1`, `M3`, `M5`, and `M6` as a final scan rather than introducing new rules.

## Nano mapping

Decision rules:

- `N1` Choose the business-logic pattern deliberately: simple flows get simpler patterns and rich rules get domain models. Source: `Choosing the Business Logic Pattern` (60-96).
- `N2` Use service layer for workflow and keep controllers thin. Source: `Application Workflow Rules / Service Layer` (99-107), `Forbidden Patterns / Controller-Centric Enterprise App` (304-306).
- `N3` Match the persistence pattern to complexity instead of defaulting to generic repositories or ORM-driven design. Source: `Persistence Pattern Rules` (132-165), `Forbidden Patterns / Generic Repository Everywhere` (296-299), `Forbidden Patterns / ORM-Driven Everything` (300-303).
- `N4` Make transaction boundaries and locking strategy explicit. Source: `Concurrency and Transaction Rules` (189-209).
- `N5` Treat remote boundaries as coarse-grained and expensive. Source: `Application Workflow Rules / Remote Facade` (108-118), `Distribution Rules` (235-248), `Forbidden Patterns / Distributed Object Fantasy` (307-309).

Trigger rules:

- `N6` When adding a repository, prove it hides meaningful persistence complexity. Source: `Persistence Pattern Rules` (132-165), `Forbidden Patterns / Generic Repository Everywhere` (296-299).
- `N7` When a simple flow grows rich rules, revisit the pattern choice. Source: `Choosing the Business Logic Pattern` (60-96).
- `N8` When remote calls become chatty, redesign the boundary. Source: `Distribution Rules` (235-248), `Forbidden Patterns / Distributed Object Fantasy` (307-309).

Final checklist:

- The checklist restates `N1`, `N3`, `N4`, and `N5` as a final scan rather than introducing new rules.

## Section coverage review

- `Purpose` (3-19): framing merged into `When to use`, `Primary bias to correct`, and `M1`.
- `Primary Directive` (20-37): covered by `M1`, `M3`, `M5`, and `M6`.
- `Architectural Baseline` (38-59): covered by `M2` and `N2`.
- `Choosing the Business Logic Pattern` (60-96): covered by `M1`, `M8`, `N1`, and `N7`.
- `Application Workflow Rules` (97-131): covered by `M2`, `M9`, `N2`, and `N5`.
- `Persistence Pattern Rules` (132-165): covered by `M3`, `M7`, `N3`, and `N6`.
- `Identity, Caching, and Unit-of-Work Rules` (166-188): covered by `M4`.
- `Concurrency and Transaction Rules` (189-209): covered by `M5`, `M10`, and `N4`.
- `Presentation Layer Rules` (210-220): covered by `M2` and `N2`.
- `Offline and Integration Rules` (221-234): covered by `M6`.
- `Distribution Rules` (235-248): covered by `M2`, `M6`, `M9`, `N5`, and `N8`.
- `Code Generation Rules` (249-273): covered by `M1`-`M6`; standalone prose is intentionally lost.
- `Review Rules` (274-290): covered by `M1`, `M3`, `M5`, and `M6`; collapsed into trigger rules and checklist.
- `Forbidden Patterns` (291-316): covered by `M2`, `M3`, `M5`, `M6`, `M7`, `M9`, `M10`, `N2`, `N3`, `N5`, `N6`, and `N8`.
- `Testing Rules` (317-326): covered by `M3`, `M5`, and `M6`; collapsed into trigger rules and checklist.
- `Review Checklist` (327-344): covered by `M1`, `M3`, `M5`, and `M6`; collapsed into the final checklist.
- `Final Instruction` (345-354): covered by `M1`, `M3`, `M5`, and `M6`.
