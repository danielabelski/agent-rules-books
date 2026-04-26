# Code Complete: Nano

## When to use

Use when you want a small always-on construction discipline.

## Primary bias to correct

A working implementation can still be structurally careless.

## Decision rules

- Choose clarity over cleverness.
- Keep routines cohesive and interfaces small.
- Validate external input; use assertions or contracts for programmer assumptions.
- Keep invalid states visible and the normal path readable.
- Replace repetitive stable branching with table-driven logic when it clarifies the rule.
- Use constants or richer types instead of magic values and ambiguous state.

## Trigger rules

- When input crosses a trust boundary, decide what gets validated.
- When a routine mixes several phases, split the concerns.
- When branches multiply, consider a table.
- When a value carries hidden meaning, model it.
- When a comment explains obvious mechanics, rewrite the code or delete the comment.

## Final checklist

- Clear?
- Defended?
- Readable normal path?
- Comments purposeful?
- Explicit?
