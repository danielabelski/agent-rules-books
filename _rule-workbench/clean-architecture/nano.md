# Clean Architecture: Nano

## When to use

Use when the main risk is framework leakage or unstable dependencies shaping core logic.

## Primary bias to correct

Framework-first structure is not architecture.

## Decision rules

- Business rules must not depend on frameworks, databases, UI, or vendor SDKs.
- Domain owns policy and invariants, application orchestrates use cases, adapters translate, infrastructure implements details.
- Define the use case and plain boundary models before wiring external details.
- Put volatile dependencies behind ports and keep composition at the edge.
- Prefer feature and use-case structure over controller/service/repository buckets.
- Test the core independently and test adapters at real boundaries.

## Trigger rules

- When framework or ORM types enter core code, move translation outward.
- When a controller, job, repository, or god service grows business rules, move them inward and split by use case.
- When a new dependency or shortcut would couple the core to a vendor or bypass the intended path, add a port and restore the boundary.

## Final checklist

- Stable core?
- Invariants inside the core?
- Use case visible?
- Details at the edge?
