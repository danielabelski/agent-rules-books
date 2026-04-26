# Domain-Driven Design Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Re-run under the generalized `PROCESS.md` on 2026-04-26 after adding `Process vs Book Diagnosis`.
- This rerun found no new process bug and no new book-specific miss; existing `min.md` and `nano.md` already preserve the book thesis and repeated micro-decisions.
- `min.md` and `nano.md` stayed unchanged on this rerun.
- Detailed artifact, review, and output-format wording stays compressed because the operational DDD pressure already survives through model discovery, bounded contexts, invariants, strategic focus, and anti-fake-DDD rules.

## Min mapping

Decision rules:

- `M1` Use DDD only where the domain needs a deep model; start with knowledge crunching and model discovery instead of plumbing-first design. Source: `What DDD Means in This Repository` (36-57), `Knowledge Crunching and Deep Models` (58-80), `Breakthrough and Deeper Insight` (103-123).
- `M2` Enforce ubiquitous language and make implicit concepts explicit. Source: `Making Implicit Concepts Explicit` (124-143), `Ubiquitous Language` (144-171), `Communication Artifacts` (172-191), `Scenario Walkthroughs` (192-211).
- `M3` Model bounded contexts and context maps deliberately; do not share one model across different meanings. Source: `Bounded Contexts` (212-233), `Strategic Design` (234-257), `Model Integrity Patterns` (258-287), `Distillation` (288-316).
- `M4` Protect invariants inside expressive entities, value objects, and aggregates with valid construction and small consistency boundaries. Source: `Entities` (369-395), `Value Objects` (396-429), `Aggregates` (457-482), `Explicit Concepts and Specifications` (507-528).
- `M5` Use repositories, factories, domain services, specifications, and domain events only when they express domain meaning, not as generic plumbing. Source: `Domain Services` (483-506), `Explicit Concepts and Specifications` (507-528), `Repositories` (529-556), `Factories` (557-576), `Domain Events` (577-603).
- `M6` Keep the application layer thin, infrastructure outside, and translations explicit at boundaries. Source: `Application Layer` (604-627), `Infrastructure` (628-643), `Translation at Boundaries` (644-663).
- `M7` Distill and protect the core domain; let supporting and generic areas stay simpler. Source: `Strategic Design` (234-257), `Distillation` (288-316), `Strategic Decision Making` (346-368).
- `M8` Prefer supple, model-driven design over anemic models, ORM-driven shapes, and fake DDD ceremony. Source: `Model-Driven Design` (81-102), `Supple Design` (664-689), `Forbidden Patterns` (842-892).

Trigger rules:

- `M9` When business terms are overloaded or teams argue about meaning, pause and refine the language before extending the model. Source: `Making Implicit Concepts Explicit` (124-143), `Ubiquitous Language` (144-171), `Scenario Walkthroughs` (192-211).
- `M10` When a transaction wants to touch many objects, decide whether the invariant is local, eventual, or split across contexts. Source: `Aggregates` (457-482), `Application Layer` (604-627), `Translation at Boundaries` (644-663).
- `M11` When persistence or transport shapes start dictating the model, reassert the domain boundary and add translation. Source: `Repositories` (529-556), `Application Layer` (604-627), `Infrastructure` (628-643), `Translation at Boundaries` (644-663), `Forbidden Patterns / ORM-Driven Design` (854-858).
- `M12` When a service accumulates decisions that sound like business policy, make the missing concept or invariant explicit in the model. Source: `Domain Services` (483-506), `Explicit Concepts and Specifications` (507-528), `Forbidden Patterns / God Services` (867-870).

Final checklist:

- The checklist restates `M2`, `M3`, `M4`, and `M7` as a final scan rather than introducing new rules.

## Nano mapping

Decision rules:

- `N1` Use DDD only where the domain needs a deep model. Source: `What DDD Means in This Repository` (36-57), `Knowledge Crunching and Deep Models` (58-80).
- `N2` Use ubiquitous language and make implicit concepts explicit. Source: `Making Implicit Concepts Explicit` (124-143), `Ubiquitous Language` (144-171).
- `N3` Model bounded contexts and do not share one model across different meanings. Source: `Bounded Contexts` (212-233), `Strategic Design` (234-257).
- `N4` Protect invariants inside expressive entities, value objects, and small aggregates. Source: `Entities` (369-395), `Value Objects` (396-429), `Aggregates` (457-482).
- `N5` Keep application orchestration thin, infrastructure outside, and translation explicit at boundaries. Source: `Application Layer` (604-627), `Infrastructure` (628-643), `Translation at Boundaries` (644-663).
- `N6` Do not do fake DDD: no anemic model, no ORM-driven design, and no pattern cargo cult. Source: `Supple Design` (664-689), `Forbidden Patterns` (842-892).

Trigger rules:

- `N7` When language is fuzzy, refine the model before coding more flows. Source: `Making Implicit Concepts Explicit` (124-143), `Ubiquitous Language` (144-171).
- `N8` When transactions sprawl, revisit the aggregate or context boundary. Source: `Aggregates` (457-482), `Bounded Contexts` (212-233).
- `N9` When storage shape drives the model, add translation and reclaim the domain. Source: `Translation at Boundaries` (644-663), `Forbidden Patterns / ORM-Driven Design` (854-858).

Final checklist:

- The checklist restates `N2`, `N3`, and `N4` as a final scan rather than introducing new rules.

## Section coverage review

- `Purpose` (3-18): framing merged into `When to use`, `Primary bias to correct`, and `M1`.
- `Primary Directive` (19-35): covered by `M1`, `M3`, `M4`, and `M8`.
- `What DDD Means in This Repository` (36-57): covered by `M1` and `N1`.
- `Knowledge Crunching and Deep Models` (58-80): covered by `M1` and `N1`.
- `Model-Driven Design` (81-102): covered by `M8`.
- `Breakthrough and Deeper Insight` (103-123): covered by `M1`.
- `Making Implicit Concepts Explicit` (124-143): covered by `M2`, `M9`, `N2`, and `N7`.
- `Ubiquitous Language` (144-171): covered by `M2`, `M9`, `N2`, and `N7`.
- `Communication Artifacts` (172-191): covered by `M2`.
- `Scenario Walkthroughs` (192-211): covered by `M2` and `M9`.
- `Bounded Contexts` (212-233): covered by `M3`, `N3`, and `N8`.
- `Strategic Design` (234-257): covered by `M3`, `M7`, and `N3`.
- `Model Integrity Patterns` (258-287): covered by `M3`.
- `Distillation` (288-316): covered by `M3` and `M7`.
- `Large-Scale Structure` (317-345): covered by `M3` and `M7`; deeper structural pattern detail is intentionally lost.
- `Strategic Decision Making` (346-368): covered by `M7`.
- `Entities` (369-395): covered by `M4` and `N4`.
- `Value Objects` (396-429): covered by `M4` and `N4`.
- `Associations and Modules` (430-456): covered by `M3` and `M6`.
- `Aggregates` (457-482): covered by `M4`, `M10`, `N4`, and `N8`.
- `Domain Services` (483-506): covered by `M5` and `M12`.
- `Explicit Concepts and Specifications` (507-528): covered by `M4`, `M5`, and `M12`.
- `Repositories` (529-556): covered by `M5` and `M11`.
- `Factories` (557-576): covered by `M5`.
- `Domain Events` (577-603): covered by `M5`.
- `Application Layer` (604-627): covered by `M6`, `M10`, `M11`, and `N5`.
- `Infrastructure` (628-643): covered by `M6`, `M11`, and `N5`.
- `Translation at Boundaries` (644-663): covered by `M6`, `M10`, `M11`, `N5`, and `N9`.
- `Supple Design` (664-689): covered by `M8` and `N6`.
- `Analysis and Model Patterns` (690-714): covered by `M8`; detailed pattern catalog is intentionally lost.
- `Code Generation Rules` (715-765): covered by `M1`, `M4`, `M6`, `M7`, and `M8`.
- `Review Rules` (766-812): covered by `M2`, `M3`, `M4`, `M5`, `M6`, and `M8`; collapsed into trigger rules and checklist.
- `Testing Rules` (813-841): covered by `M4`, `M6`, and `M8`; collapsed into trigger rules and checklist.
- `Forbidden Patterns` (842-892): covered by `M8`, `M11`, `M12`, `N6`, and `N9`.
- `Refactoring Rules` (893-913): covered by `M3`, `M4`, `M6`, and `M8`.
- `Output Expectations` (914-949): covered by `M1`, `M4`, `M5`, `M6`, and `M7`; standalone prose is intentionally lost.
- `Review Checklist` (950-976): covered by `M2`, `M3`, `M4`, and `M7`; collapsed into the final checklist.
- `Final Instruction` (977-986): covered by `M1`, `M3`, `M4`, and `M8`.
