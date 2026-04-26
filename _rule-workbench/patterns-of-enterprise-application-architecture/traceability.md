# Patterns of Enterprise Application Architecture Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Dropped from `nano.md` as secondary: detailed pattern catalogs that do not change the first architectural choice under tight context.
- Kept whenever a rule changes business-logic pattern choice, persistence pattern choice, transaction boundaries, or remote-boundary design.
- Merged the long pattern taxonomy into a smaller set of pattern-selection rules and triggers.

## Min mapping

- `M1` Choose the business-logic pattern deliberately: transaction script for simple workflows, table module for table-centric logic, domain model for rich invariants and behavior. Source: `Choosing the Business Logic Pattern` (60-96).
- `M2` Use service layer for application workflow and keep controllers thin; use remote facades and DTOs only when crossing expensive or unstable boundaries. Source: `Application Workflow Rules` (97-131), `Distribution Rules` (235-248).
- `M3` Match the persistence pattern to complexity: Active Record is acceptable for simple CRUD, Data Mapper and Repository are for richer separation needs. Source: `Persistence Pattern Rules` (132-165), `Forbidden Patterns / Generic Repository Everywhere` (296-299), `Forbidden Patterns / ORM-Driven Everything` (300-303).
- `M4` Use Unit of Work, Identity Map, and Lazy Load deliberately and visibly, not as invisible magic that changes consistency or performance expectations. Source: `Identity, Caching, and Unit-of-Work Rules` (166-188).
- `M5` Make transaction boundaries and locking strategy explicit around real contention and consistency needs. Source: `Concurrency and Transaction Rules` (189-209), `Forbidden Patterns / Transaction Chaos` (310-313).
- `M6` Keep integration and distribution coarse-grained and explicit; do not design as if remote calls were cheap local method calls. Source: `Offline and Integration Rules` (221-234), `Distribution Rules` (235-248), `Forbidden Patterns / Distributed Object Fantasy` (307-309).

## Nano mapping

- `N1` Choose the business-logic pattern deliberately: transaction script for simple flows, domain model for rich rules. Source: `Choosing the Business Logic Pattern` (60-96).
- `N2` Use service layer for workflow and keep controllers thin. Source: `Application Workflow Rules / Service Layer` (99-107), `Forbidden Patterns / Controller-Centric Enterprise App` (304-306).
- `N3` Match the persistence pattern to complexity instead of defaulting to generic repositories or ORM-driven design. Source: `Persistence Pattern Rules` (132-165), `Forbidden Patterns / Generic Repository Everywhere` (296-299), `Forbidden Patterns / ORM-Driven Everything` (300-303).
- `N4` Make transaction boundaries and locking strategy explicit. Source: `Concurrency and Transaction Rules` (189-209).
- `N5` Treat remote boundaries as coarse-grained and expensive. Source: `Application Workflow Rules / Remote Facade` (108-118), `Distribution Rules` (235-248), `Forbidden Patterns / Distributed Object Fantasy` (307-309).

## Intentional omissions

- Detailed mentions of `Row Data Gateway`, `Table Data Gateway`, and some presentation-layer specifics: preserved conceptually inside persistence and workflow choices, but not spelled out in `nano.md`.
- `Testing Rules` (317-326) and `Review Checklist` (327-344): collapsed into triggers and checklist.
