# Rule Compression Process

## Goal

Create compressed rule sets that are decision-equivalent to the full source, not sentence-equivalent.

The compressed versions should preserve the rules that materially change an AI agent's design, architecture, refactoring, review, and risk decisions under context pressure.

## Source of Truth

- The canonical full rule set stays in the main book directory.
- Each workbench directory exposes it as `full.md` via symlink.
- Do not edit `full.md` in the workbench.
- `min.md` and `nano.md` must always trace back to the canonical full source through `traceability.md`.

## Deliverables Per Book

- `full.md`: canonical full source by symlink
- `traceability.md`: what was kept, merged, or omitted, with references to source sections
- `min.md`: on-demand compressed version
- `nano.md`: always-on version for tight context budgets

## Rule Classification

For each source section, classify rules before compressing:

- `default`: good hygiene many capable agents already follow without being told
- `decision-changing`: changes architecture, modeling, persistence, error handling, operational, or refactoring decisions
- `conflict-resolver`: resolves tradeoffs such as simple vs rich model, local fix vs strategic fix, retry vs idempotency
- `trigger`: activates only when touching a risky area
- `checklist-only`: useful as a final scan, but too weak as a main rule
- `framing`: useful context, but not an operational rule

## Compression Rules

### Build `min.md`

- Keep every `decision-changing`, `conflict-resolver`, and strong `trigger` rule.
- Remove `default` rules unless they counter a known model failure mode.
- Merge duplicated rules across purpose, codegen, review, testing, and forbidden-pattern sections.
- Prefer short operational rules over explanatory prose.
- Convert long review and testing lists into trigger rules and a final checklist.

### Build `nano.md`

- Keep only rules safe for always-on attachment in a constrained context budget.
- Keep rules that correct known model biases:
  - shallow wrappers mistaken for good abstraction
  - framework-first design
  - unsafe retries
  - rewrite-first legacy work
  - fake DDD or fake layering
  - hidden consistency contracts
- Drop generic readability, formatting, and obvious hygiene unless their absence causes known failures.
- Keep trigger rules that prevent shortcuts in risky areas.

## Traceability Rules

- Every retained rule in `min.md` gets an `M*` id in `traceability.md`.
- Every retained rule in `nano.md` gets an `N*` id in `traceability.md`.
- Each id must reference the source section names and current line ranges in `full.md`.
- Record intentional omissions, especially when whole sections are collapsed into one compressed rule.

## Preferred Output Shape

Use the same structure for `min.md` and `nano.md`:

1. title
2. when to use
3. primary bias to correct
4. decision rules
5. trigger rules
6. final checklist

## Validation Checklist

Before considering a book done:

- the canonical full source is untouched
- each retained rule changes a real agent decision or blocks a known failure mode
- duplicate guidance is merged
- long lists are collapsed into triggers or checklist items
- `nano.md` can stand alone as an always-on attachment
- `min.md` still preserves the book's unique point of view
- `traceability.md` explains why anything important was removed or merged

## Interpretation Heuristics

- Prefer rules that affect boundaries, invariants, data ownership, failure semantics, and refactoring safety.
- Prefer explicit tradeoff rules over generic quality slogans.
- Keep book-specific biases visible. Compression must not turn all books into the same generic style guide.
- If a rule matters only while touching a specific hotspot, move it into trigger form.
- If a rule is obvious but agents still commonly violate it, keep it.
- When unsure, keep a rule in `min.md`; make `nano.md` stricter.
