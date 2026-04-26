# Usage

This repository ships three versions of every rule set:

- `nano`: the always-on version for tight context budgets
- `min`: the stronger on-demand version
- `full`: the complete reference version

## Start Here

Use the smallest mechanism that still changes the agent's decisions.

- Start with one primary rule set.
- Use `nano` as the default always-on layer.
- Add `min` only when the current task needs stronger book-specific pressure.
- Use `full` for audits, one-off deep sessions, or for deriving smaller scoped rules.
- Prefer scoped, on-demand, or retrieval-based loading over global loading.
- Treat memories as helpers, not as the canonical source of truth.

## Delivery Patterns

| Pattern | Best for | Repo version | Notes |
| --- | --- | --- | --- |
| Always-on project rule | Stable defaults that should affect most tasks | `nano` | Keep this short. |
| Scoped rule | One directory, file type, or subsystem | `nano` or `min` | Better than inflating the global prompt. |
| On-demand rule | Refactoring passes, reviews, migrations, reliability work | `min` | Invoke only when the task matches. |
| Skill or command | Multi-step procedures, checklists, workflows with examples | Usually derived from `min` | Better than storing procedures in a global rule file. |
| Retrieval or MCP | Large reference material, changing docs, external systems | `full` or source material outside the prompt | Use when the content is too large or too rarely needed for always-on context. |

## Portable Baseline

If your team uses more than one editor, use a portable baseline:

- Keep one canonical `AGENTS.md` with a single `nano` rule set.
- Let Codex read that file directly.
- Let Claude Code import it from `CLAUDE.md`.
- Let Cursor either read `AGENTS.md` directly for simple projects or translate the same content into `.cursor/rules` for better scoping.
- Add editor-specific on-demand mechanisms next to that baseline instead of duplicating a large global rule file.

This gives you one cross-tool source for the base layer, while still allowing each editor to use its stronger native features.

## Codex

### Available mechanisms

- `AGENTS.md` in the repo root or nested directories
- `AGENTS.override.md` for closer overrides
- `.codex/config.toml` with `model_instructions_file`, `project_doc_fallback_filenames`, and project-scoped config
- skills in `.agents/skills/` or `~/.agents/skills/`
- hooks via `.codex/config.toml` or `hooks.json`
- MCP servers and web search for external context
- memories for learned preferences

### Preferred setup

Use Codex in two layers:

1. Put one `nano` rule set in the always-on project layer.
2. Use skills, nested instructions, or focused sessions for stronger and narrower guidance.

Preferred order:

1. Use root `AGENTS.md` for the project-wide base layer.
2. Use `model_instructions_file` if you want Codex to point at a chosen file without renaming it to `AGENTS.md`.
3. Add nested `AGENTS.md` or `AGENTS.override.md` only where a subtree genuinely needs different pressure.
4. Turn procedures, checklists, and reference-heavy workflows into skills.
5. Use MCP or retrieval for large reference corpora instead of stuffing them into the always-on file.

### Recommended version mapping

- `nano`: project-wide default in `AGENTS.md` or `model_instructions_file`
- `min`: skill, nested rule file, or temporary focused session
- `full`: reference only

### Recommended structure

```text
project/
  AGENTS.md
  .agents/
    skills/
      refactoring-pass/
        SKILL.md
  services/
    payments/
      AGENTS.override.md
```

### Use Codex this way when

- you want a stable repo-wide engineering bias
- some subtrees need different guidance
- a workflow is repeatable enough to deserve a skill

### Avoid

- loading several `full` files globally
- putting long procedures into `AGENTS.md`
- using memories as the primary place for shared rules

## Claude Code

### Available mechanisms

- `CLAUDE.md` or `.claude/CLAUDE.md`
- `CLAUDE.local.md` for private local additions
- `@path` imports inside `CLAUDE.md`
- `.claude/rules/` for scoped project rules
- `.claude/skills/<name>/SKILL.md`
- subagents
- hooks in settings or scoped to skills
- MCP resources and prompts
- auto memory

### Preferred setup

Claude Code works best with a small root memory file plus scoped additions.

Preferred order:

1. Keep root `CLAUDE.md` short.
2. If you want one shared cross-tool base file, put the chosen repo file at `AGENTS.md` and import it from `CLAUDE.md`.
3. Use one `nano` rule set for always-on project context.
4. Use `.claude/rules/` or path-scoped skills for `min`.
5. Put procedures, large checklists, and long references into skills instead of the root `CLAUDE.md`.
6. Use `disable-model-invocation: true` for side-effectful manual workflows such as deploy or release flows.
7. Use subagents or `context: fork` skills when a side task would otherwise flood the main context.

### Recommended version mapping

- `nano`: imported from `CLAUDE.md` or written directly into it
- `min`: `.claude/rules/` or `.claude/skills/`
- `full`: reference only, or a narrowly imported file for a specific session

### Recommended structure

```text
project/
  AGENTS.md
  CLAUDE.md
  .claude/
    rules/
    skills/
```

Example `CLAUDE.md`:

```md
@AGENTS.md

## Claude Code

- Use skills for long procedures and checklists.
- Use scoped rules for subsystem-specific guidance.
```

### Use Claude Code this way when

- you want a cross-tool base layer plus Claude-specific scoping
- a rule only matters in one subsystem
- a rule has become a procedure rather than a fact

### Avoid

- pasting a long `full` rule file into root `CLAUDE.md`
- mixing many conflicting imports
- relying on auto memory instead of reviewed project instructions

## Cursor

### Available mechanisms

- `.cursor/rules/*.mdc` project rules
- rule types: `Always`, `Auto Attached`, `Agent Requested`, `Manual`
- root `AGENTS.md` as a simple alternative
- user rules
- `@Cursor Rules` for explicit rule application
- `/Generate Cursor Rules`
- memories
- codebase indexing
- MCP

### Preferred setup

Cursor's strongest native mechanism is `.cursor/rules`.

Preferred order:

1. Prefer `.cursor/rules` over `AGENTS.md` for serious use.
2. Use at most one short `Always` rule for project-wide `nano` guidance.
3. Turn `min` into `Agent Requested`, `Manual`, or `Auto Attached` rules by topic or path.
4. Use `@Cursor Rules` when you want explicit on-demand application.
5. Keep large reference material in attached files, indexed docs, or MCP, not in `Always` rules.
6. Use root `AGENTS.md` only for simple projects or when you want a portable cross-tool baseline.

### Recommended version mapping

- `nano`: short `Always` rule or simple root `AGENTS.md`
- `min`: `Agent Requested`, `Manual`, or `Auto Attached` project rules
- `full`: reference only

### Recommended structure

```text
project/
  .cursor/
    rules/
      base.mdc
      payments.mdc
      refactor.mdc
      ddd.mdc
```

Suggested split:

- `base.mdc`: one short `Always` rule derived from `nano`
- `payments.mdc`: `Auto Attached` for `payments/**`
- `refactor.mdc`: `Manual` for explicit refactoring passes
- `ddd.mdc`: `Agent Requested` for modeling-heavy tasks

### Use Cursor this way when

- you want strong scoping and explicit control over context
- you want different rules for different subsystems
- you want on-demand rule selection without a huge global file

### Avoid

- using one giant `Always` rule
- treating root `AGENTS.md` as the best default for complex projects
- storing large reference packs in project rules when indexing or MCP is a better fit

## Retrieval, MCP, and RAG

Use retrieval-based delivery when the material is too large, too dynamic, or too rarely needed for always-on context.

Good candidates:

- multiple books at once
- large examples and templates
- architecture docs, specs, and runbooks
- changing external guidance
- domain documents that matter only for some tasks

Recommended by editor:

- Codex: skills plus MCP or retrieval-backed tools
- Claude Code: skills plus MCP resources or prompts, optionally with subagents
- Cursor: scoped project rules plus codebase indexing or MCP

If your team already has a RAG system, keep the long reference material there and only promote decision-changing rules into always-on or scoped prompt rules.

## Decision Guide

- Need a steady repo-wide bias: use one `nano` rule set.
- Need stronger guidance for a specific task: load `min` on demand.
- Need a multi-step workflow: create a skill or command.
- Need subsystem-specific pressure: use scoped rules or nested files.
- Need long reference material: use retrieval, indexing, or MCP.
- Need more than one book: keep one primary always-on rule set and move the rest to on-demand mechanisms.
