# Clean Architecture Traceability

Canonical full source: [full.md](full.md)

## Compression decisions

- Dropped from `nano.md` as default or secondary: detailed naming, output-format, and preferred-shape examples.
- Kept whenever a rule changes dependency direction, layer ownership, boundary models, or testing strategy.
- Merged the detailed layer descriptions, codegen rules, and forbidden patterns into a smaller set of architectural constraints and triggers.

## Min mapping

- `M1` Enforce the dependency rule: business rules depend inward only. Source: `Non-Negotiable Rules` (19-73), `Architecture Heuristics / Dependency Direction` (215-223), `Forbidden Patterns / Direction Violations` (333-337).
- `M2` Keep domain pure, application orchestration focused, adapters translational, and infrastructure replaceable. Source: `Required Layer Responsibilities` (74-155), `Architecture Heuristics / Policy vs Detail` (224-232).
- `M3` Define the use case and plain boundary models before wiring frameworks or storage. Source: `Code Generation Rules` (156-212), especially `Define the Use Case First` (160-176) and `Use Plain Models at Boundaries` (177-181).
- `M4` Put volatile dependencies behind ports and keep wiring at the edge. Source: `Create Ports for Volatile Dependencies` (182-195), `Keep Wiring in the Main Component` (196-200), `Stable Core, Replaceable Edge` (233-243).
- `M5` Structure by feature and use case, not by framework buckets. Source: `Feature First Structure` (244-260), `Preferred Default Shapes` (422-449).
- `M6` Test core policy without real infrastructure and test adapters at supported boundaries. Source: `Testing Rules` (272-303).

## Nano mapping

- `N1` Business rules must not depend on frameworks, databases, UI, or vendor SDKs. Source: `Non-Negotiable Rules` (19-73).
- `N2` Domain owns policy, application orchestrates use cases, adapters translate, infrastructure implements details. Source: `Required Layer Responsibilities` (74-155).
- `N3` Define use cases and plain boundary models before framework wiring. Source: `Code Generation Rules` (156-212).
- `N4` Put volatile dependencies behind ports and keep composition at the edge. Source: `Create Ports for Volatile Dependencies` (182-195), `Keep Wiring in the Main Component` (196-200).
- `N5` Test the core independently and test adapters through real boundaries. Source: `Testing Rules` (272-303).

## Intentional omissions

- `Naming Rules` (261-271): useful, but not distinctively architectural under tight context.
- `Output Expectations` (375-399) and `Review Checklist` (400-421): collapsed into trigger rules and checklist.
- `When Tradeoffs Are Necessary` (450-461): folded into the dependency and use-case rules above.
