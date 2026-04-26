# Clean Architecture: Nano

## When to use

Use when the main risk is framework leakage or unstable dependencies shaping core logic.

## Primary bias to correct

Framework-first structure is not architecture.

## Decision rules

- Business rules must not depend on frameworks, databases, UI, or vendor SDKs.
- Domain owns policy, application orchestrates use cases, adapters translate, infrastructure implements details.
- Define the use case and plain boundary models before wiring external details.
- Put volatile dependencies behind ports and keep wiring at the edge.
- Test the core independently from infrastructure.

## Trigger rules

- When framework or ORM types enter core code, move translation outward.
- When a controller or job grows business rules, move them inward.
- When a new dependency would couple the core to a vendor, add a port.

## Final checklist

- Stable core?
- Details at the edge?
- Use case visible?
