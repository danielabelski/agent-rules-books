# The Pragmatic Programmer: Nano

## When to use

Use when you need a compact general engineering bias toward adaptability and feedback.

## Primary bias to correct

Local code changes still have system-level consequences.

## Decision rules

- Own the result beyond the local edit.
- DRY means one authoritative place per piece of knowledge.
- Preserve orthogonality so changes stay local.
- Use tracer bullets and prototypes to learn quickly, but do not fossilize them.
- Automate repeatable work and shorten feedback loops.
- Make important assumptions explicit and leave touched code slightly better than before.

## Trigger rules

- When knowledge is copied, choose one owner.
- When changes fan out widely, look for missing orthogonality.
- When manual steps or hidden assumptions repeat, automate them or encode them explicitly.

## Final checklist

- One owner?
- Localized change?
- Faster loop?
- Touched area better?
