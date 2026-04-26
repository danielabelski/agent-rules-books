# Domain-Driven Design Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Dropped from `minimal.md` as secondary: detailed artifact, output, and review formatting guidance.
- Kept whenever a rule changes model discovery, bounded-context boundaries, invariant placement, translation, or strategic prioritization.
- Merged many repeated `Rules / Required behavior / Anti-patterns` triplets into fewer higher-leverage rules with explicit triggers.

## Optimal mapping

- `O1` Use DDD only where the domain needs a deep model; start with knowledge crunching and model discovery instead of plumbing-first design. Source: `What DDD Means in This Repository` (36-57), `Knowledge Crunching and Deep Models` (58-80), `Breakthrough and Deeper Insight` (103-123).
- `O2` Enforce ubiquitous language and make implicit concepts explicit. Source: `Making Implicit Concepts Explicit` (124-143), `Ubiquitous Language` (144-171), `Communication Artifacts` (172-191), `Scenario Walkthroughs` (192-211).
- `O3` Model bounded contexts and context maps deliberately; do not share one model across different meanings. Source: `Bounded Contexts` (212-233), `Strategic Design` (234-257), `Model Integrity Patterns` (258-287), `Distillation` (288-316).
- `O4` Protect invariants inside expressive entities, value objects, and aggregates with valid construction and small consistency boundaries. Source: `Entities` (369-395), `Value Objects` (396-429), `Aggregates` (457-482), `Explicit Concepts and Specifications` (507-528).
- `O5` Use repositories, factories, domain services, and domain events only when they express domain meaning, not as generic plumbing. Source: `Domain Services` (483-506), `Repositories` (529-556), `Factories` (557-576), `Domain Events` (577-603).
- `O6` Keep the application layer thin, infrastructure outside, and translations explicit at boundaries. Source: `Application Layer` (604-627), `Infrastructure` (628-643), `Translation at Boundaries` (644-663).
- `O7` Distill and protect the core domain; let supporting and generic areas stay simpler. Source: `Strategic Design / Core Domain` (236-240), `Distillation` (288-316), `Strategic Decision Making` (346-368).
- `O8` Prefer supple, model-driven design over anemic models, ORM-driven shapes, and fake DDD ceremony. Source: `Model-Driven Design` (81-102), `Supple Design` (664-689), `Forbidden Patterns` (842-892).

## Minimal mapping

- `M1` Use DDD only where the domain needs a deep model. Source: `What DDD Means in This Repository` (36-57), `Knowledge Crunching and Deep Models` (58-80).
- `M2` Use ubiquitous language and make implicit concepts explicit. Source: `Making Implicit Concepts Explicit` (124-143), `Ubiquitous Language` (144-171).
- `M3` Model bounded contexts and do not share one model across different meanings. Source: `Bounded Contexts` (212-233), `Strategic Design` (234-257).
- `M4` Protect invariants inside expressive entities, value objects, and small aggregates. Source: `Entities` (369-395), `Value Objects` (396-429), `Aggregates` (457-482).
- `M5` Keep application orchestration thin, infrastructure outside, and translation explicit at boundaries. Source: `Application Layer` (604-627), `Infrastructure` (628-643), `Translation at Boundaries` (644-663).
- `M6` Do not do fake DDD: no anemic model, no ORM-driven design, no pattern cargo cult. Source: `Forbidden Patterns` (842-892), `Supple Design` (664-689).

## Intentional omissions

- `Large-Scale Structure` (317-345) and parts of `Analysis and Model Patterns` (690-714): important, but too specialized for `minimal.md`; the essence is folded into context and model rules.
- `Testing Rules` (813-841), `Review Rules` (766-812), `Output Expectations` (914-949), and `Review Checklist` (950-976): collapsed into triggers and checklist.
