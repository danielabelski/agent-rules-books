# A Philosophy of Software Design: Nano

## When to use

Use when the main risk is accidental complexity, shallow abstractions, or leaky interfaces.

## Primary bias to correct

Small pieces are not automatically simple.

## Decision rules

- Optimize for lower cognitive load, not shorter files or fewer lines.
- Prefer deep modules; reject wrappers and layers that do not hide real complexity.
- Hide volatile details and messy edge handling below stable interfaces.
- Keep interfaces narrow and semantic; avoid staged APIs, flags, and mechanism leakage.
- If a change feels awkward, fix the design instead of adding tactical special cases.

## Trigger rules

- When adding a helper or layer, prove it removes complexity for callers.
- When an API requires sequencing knowledge, redesign the boundary.
- When one change spreads widely, look for hidden dependencies or the wrong abstraction.

## Final checklist

- Fewer concepts to hold?
- More complexity hidden below the boundary?
- Fewer special cases and call-order traps?
