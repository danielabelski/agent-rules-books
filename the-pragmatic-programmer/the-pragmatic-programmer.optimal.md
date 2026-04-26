# The Pragmatic Programmer: Optimal

## When to use

Use as a general engineering operating style when the goal is adaptability, fast feedback, and responsibility for outcomes.

## Primary bias to correct

Do not optimize only for the local edit; optimize for the whole result.

## Decision rules

- Own the result. Think past the file you are changing and account for operational, integration, and maintenance consequences.
- Treat DRY as single ownership of knowledge, not as cosmetic deduplication of similar text.
- Preserve orthogonality so one decision or change does not force coordinated edits across unrelated areas.
- Use tracer bullets and prototypes to learn quickly, but treat prototypes as disposable unless they have been hardened deliberately.
- Automate repeatable work and shorten feedback loops for build, test, verification, and environment setup.
- Use explicit contracts, assertions, and deliberate recovery choices where failure semantics matter.
- Apply the broken windows rule: leave touched code slightly clearer, safer, or more maintainable than before.

## Trigger rules

- When the same knowledge is copied into multiple places, choose one owner and derive the rest.
- When a change requires touching many unrelated modules, look for missing orthogonality or a hidden shared concern.
- When manual steps recur, automate them before they become tribal knowledge.
- When prototype shortcuts start leaking into durable code, either harden them or replace them.

## Final checklist

- One owner per piece of knowledge?
- Changes still local?
- Feedback loop fast enough?
- Touched code slightly better?
