# Clean Architecture: Min

## When to use

Use for systems where business rules must stay stable while frameworks, databases, transports, and vendors change.

## Primary bias to correct

Do not let framework structure or adapter convenience become the architecture.

## Decision rules

- Enforce the dependency rule: source dependencies point toward policy, never toward frameworks or delivery mechanisms.
- Keep the domain pure and put core invariants in entities or domain objects, not in controllers, jobs, repository code, or SQL.
- Let the application layer coordinate use cases, transactions, and ports. It should orchestrate business work, not become a dumping ground for policy.
- Keep adapters responsible for translation: requests to use-case input, domain results to responses, and persistence or transport models to domain-friendly shapes.
- Treat infrastructure as replaceable detail. Inner layers own the ports they need, outer layers implement them, and composition stays at the edge.
- Define the use case and its plain boundary models before wiring details. The framework code should follow the use case, not the reverse.
- Prefer feature-oriented structure and role-based names so the ownership of a use case stays visible. Avoid generic `*Service`, `Helper`, `Manager`, `Common`, or `utils` escape hatches.
- Test the core without real infrastructure. Add focused adapter tests where translation or integration behavior is the risk.

## Trigger rules

- When framework or ORM types appear in domain or use-case code, stop and move translation to an adapter.
- When a controller, handler, job, repository, or SQL path starts carrying business rules or invariant checks, move policy inward.
- When adding a new external dependency, introduce a port if the core would otherwise learn vendor or transport details.
- When a cross-layer shortcut appears or a large `*Service` starts spanning multiple actions, split by use case and restore the boundary.

## Final checklist

- Could the business rules survive a database, UI, or framework replacement?
- Are invariants protected in the core instead of adapters or infrastructure?
- Is the use case visible as a unit, with plain input and output models?
- Are risky integrations isolated outward, with ports owned inward and dependencies still pointing toward policy?
