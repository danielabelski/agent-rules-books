# Code Complete: Nano

## When to use

Use when you want a small always-on construction discipline.

## Primary bias to correct

A working implementation can still be structurally careless.

## Decision rules

- Choose clarity over cleverness.
- Keep routines cohesive and interfaces small.
- Validate external input; use assertions or contracts for programmer assumptions.
- Replace repetitive stable branching with table-driven logic when it clarifies the rule.
- Use constants or richer types instead of magic values and ambiguous state.

## Trigger rules

- When input crosses a trust boundary, decide what gets validated.
- When branches multiply, consider a table.
- When a value carries hidden meaning, model it.

## Final checklist

- Clear?
- Defended?
- Explicit?
