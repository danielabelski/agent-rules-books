# Clean Code: Min

## When to use

Use when readability, local reasoning, and maintainable code shape are the main concerns.

## Primary bias to correct

Do not preserve confusing structure just because the code already works.

## Decision rules

- Use precise names and one term per concept. Rename code when the current name hides meaning, overloads a familiar word, or forces comments to explain it.
- Keep functions cohesive and at one level of abstraction. Split behavior instead of hiding mode switches behind boolean flags or mixed responsibilities.
- Separate commands from queries and eliminate hidden side effects so callers can reason locally about what changes state.
- Keep parameters few and meaningful. If a function needs a cluster of inputs, model the concept instead of passing a grab bag.
- Use comments only for rationale, constraints, warnings, or external contracts. If a comment explains what the code is doing, improve the code instead.
- Expose behavior rather than raw representation. Avoid train-wreck access, utility dumping grounds, and arbitrary mixing of plain data and business behavior.
- When touching code, remove the smell that most directly increases change cost: duplication, deep nesting, long parameter lists, primitive obsession, hidden dependency, or misleading control flow.
- Isolate unstable external dependencies behind local boundaries when direct coupling would leak vendor quirks into the core.

## Trigger rules

- When adding a boolean flag, consider separate entry points or a richer type first.
- When adding a comment to explain code flow, simplify names or structure before keeping the comment.
- When a function both answers a question and mutates state, split the responsibilities.
- When a change requires touching many unrelated places, look for duplication, hidden dependency, or the wrong abstraction boundary.

## Final checklist

- Are the names carrying the meaning without extra narration?
- Can a reader tell what mutates state and what only reads it?
- Did the touched code get simpler instead of merely longer?
- Did I remove at least one smell that would slow the next change?
