# Working Effectively with Legacy Code: Nano

## When to use

Use when code is hard to change safely and you need a small always-on legacy discipline.

## Primary bias to correct

Legacy work starts with control, not cleanup.

## Decision rules

- The first goal is safe change, not rewrite or beauty.
- Get characterization tests or equivalent observations before changing uncertain behavior.
- Find or create seams and break dependencies explicitly.
- Prefer sprout, wrap, or similar isolating techniques over invasive rewrites.
- Do not expand hidden dependencies or perform no-safety changes.

## Trigger rules

- When behavior is uncertain, characterize first.
- When globals, statics, or constructors dominate, break one dependency at a time.
- When rewrite feels tempting, look for the next smaller seam.

## Final checklist

- Characterized?
- Isolated?
- Safer now?
