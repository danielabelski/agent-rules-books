# Code Complete: Optimal

## When to use

Use when you want disciplined construction choices during implementation, especially around defensive coding, control flow, and code shape.

## Primary bias to correct

Do not let local cleverness outrun construction discipline.

## Decision rules

- Choose clarity and maintainability over clever compactness or novelty.
- Keep routines cohesive, with small hard-to-misuse interfaces and local scope that does not carry multiple meanings.
- Use explicit validation for external input and assertions or contracts for programmer assumptions. Make invalid states visible instead of silently tolerated.
- Prefer straightforward control flow. When the logic is a stable mapping, use table-driven or data-driven structure instead of growing branch forests.
- Replace magic values and unexplained sentinels with constants, enums, richer types, or explicit optionality.
- Keep class and module responsibilities cohesive so likely changes stay local.
- Build incrementally: take small steps, review against consistency and defect risk, and avoid speculative structure that has not earned its keep.

## Trigger rules

- When adding input at a trust boundary, decide explicitly what is validated, asserted, or rejected.
- When branching expands around a stable mapping, check whether a table or policy object would make the rules clearer.
- When a variable starts carrying units, lifecycle, or status implicitly, turn that meaning into a clearer type or name.
- When tempted by a clever shortcut, prefer the version the next maintainer can debug at 2 a.m.

## Final checklist

- Clear over clever?
- Invalid states visible?
- Stable mappings explicit?
- Small reviewable step?
