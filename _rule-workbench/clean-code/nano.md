# Clean Code: Nano

## When to use

Use when you need a small always-on bias toward readable, low-surprise code.

## Primary bias to correct

Readable code is not the same as code with nice formatting.

## Decision rules

- Use precise names and one term per concept.
- Split boolean flags, mixed abstraction levels, and hidden side effects out of functions.
- Separate commands from queries.
- Use comments only for rationale or contracts, not to explain confusing code.
- When touching code, remove the smell most likely to make the next change risky or unclear.

## Trigger rules

- When a function both mutates and answers, split it.
- When a comment explains the flow, simplify the code first.
- When a change spreads, look for duplication or hidden dependency.

## Final checklist

- Clear names?
- Clear mutation boundaries?
- One smell removed?
