# Patterns of Enterprise Application Architecture: Nano

## When to use

Use when an enterprise application needs a small pattern-selection compass.

## Primary bias to correct

Pattern reuse is not pattern choice.

## Decision rules

- Choose the business-logic pattern deliberately: simple flows get simpler patterns, rich rules get domain models.
- Use service layer for workflow and keep controllers thin.
- Match the persistence pattern to complexity instead of defaulting to generic repositories or ORM-driven design.
- Make transaction boundaries and locking strategy explicit.
- Treat remote boundaries as coarse-grained and expensive.

## Trigger rules

- When adding a repository, prove it hides meaningful persistence complexity.
- When a simple flow grows rich rules, revisit the pattern choice.
- When remote calls become chatty, redesign the boundary.

## Final checklist

- Right pattern?
- Explicit transaction?
- Coarse remote boundary?
