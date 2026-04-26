# Release Process

## Goal

Release the compressed rule sets from `_rule-workbench/` into the main repository without losing traceability or making the README drift from the actual files.

## Target layout

For each book:

- keep the current canonical full file as-is:
  - `<book>/<book>.md`
- copy the compressed release files from the workbench into the book directory:
  - `_rule-workbench/<book>/optimal.md` -> `<book>/<book>.optimal.md`
  - `_rule-workbench/<book>/minimal.md` -> `<book>/<book>.minimal.md`

`traceability.md` and `full.md` stay in `_rule-workbench/` and are not part of the released public surface by default.

## Release steps

### 1. Validate the workbench

Before copying anything:

- every book must have `full.md`, `traceability.md`, `optimal.md`, and `minimal.md`
- `full.md` must still resolve to the canonical source file
- `optimal.md` and `minimal.md` must follow the structure from `PROCESS.md`
- `minimal.md` must stay small enough for always-on use
- `traceability.md` must map retained rules back to the full source

### 2. Add or update repository `README.md`

The repository README must contain a table with:

- one row per book
- grouped columns for `full`, `optimal`, and `minimal`
- for each version:
  - line count
  - rule count
  - file size
  - file link

Recommended columns:

| Book | Full lines | Full rules | Full size | Full file | Optimal lines | Optimal rules | Optimal size | Optimal file | Minimal lines | Minimal rules | Minimal size | Minimal file |
| --- | ---: | ---: | ---: | --- | ---: | ---: | ---: | --- | ---: | ---: | ---: | --- |

Recommended link targets:

- full: `<book>/<book>.md`
- optimal: `<book>/<book>.optimal.md`
- minimal: `<book>/<book>.minimal.md`

### 3. Copy files into the repository

For each book:

- keep `<book>/<book>.md` unchanged as the full version
- copy `_rule-workbench/<book>/optimal.md` to `<book>/<book>.optimal.md`
- copy `_rule-workbench/<book>/minimal.md` to `<book>/<book>.minimal.md`

After copying:

- verify that every README link resolves
- verify that metrics in README match the actual released files
- verify that no workbench-only file leaked into the release surface by accident

## Metric rules

Use deterministic metrics so README stays reproducible.

### Line count

- count physical lines in the released file
- use `wc -l`

### File size

- use raw bytes
- use `wc -c`

### Rule count

Use one deterministic rule-counting convention across all versions:

- count Markdown list items that represent actionable instructions
- include:
  - unordered list items starting with `- `
  - ordered list items like `1.`
- exclude:
  - headings
  - blank lines
  - prose paragraphs
  - code fences and code examples
  - table rows

For `optimal.md` and `minimal.md`, this corresponds to bullets under:

- `Decision rules`
- `Trigger rules`
- `Final checklist`

For `full` files, apply the same list-item counting rule consistently even if the prose density differs by book.

## Suggested release verification commands

Examples:

```bash
find _rule-workbench -maxdepth 2 -type f | sort
```

```bash
wc -l <book>/<book>.md <book>/<book>.optimal.md <book>/<book>.minimal.md
```

```bash
wc -c <book>/<book>.md <book>/<book>.optimal.md <book>/<book>.minimal.md
```

If you automate README generation later, keep the metric definitions above unchanged so historical releases remain comparable.

## Non-goals

- Do not edit the canonical full files during release.
- Do not treat `traceability.md` as public release content unless there is a separate decision to expose it.
- Do not change the metric definitions between releases without also updating this document and regenerating README consistently.
