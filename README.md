# AGENTS Book Rules

![AGENTS Book Rules](books-ai-rules.png)

MIT licensed universal project rules for coding agents.

This repository contains ready-to-use rule sets inspired by well-known books on software design, architecture, refactoring, legacy code, reliability, and data-intensive systems.

For constructive criticism from Reddit, see [CRITICISM.md](CRITICISM.md).
For editor-specific setup in Codex, Claude Code, and Cursor, see [USAGE.md](USAGE.md). It covers always-on vs on-demand usage, skills, scoped rules, MCP or RAG patterns, and the preferred setup for each editor.

Each rule set is released in three tool-agnostic Markdown versions:

- `full`: the canonical complete source
- `optimal`: the compressed on-demand version
- `minimal`: the compressed always-on version for tight context budgets

## Quick Start

- start with one primary rule set in `minimal`
- open [USAGE.md](USAGE.md) and follow the setup for Codex, Claude Code, or Cursor
- keep `minimal` as the always-on base layer
- switch to `optimal` only when the task needs more book-specific pressure
- use `full` for reference, audits, or for deriving narrower scoped rules or skills
- avoid loading every rule at once

## Release Matrix

Metrics:

- `lines`: physical line count from `wc -l`
- `rules`: Markdown list items counted with the deterministic release convention
- `size`: raw bytes from `wc -c`

| Rule Set | Full lines | Full rules | Full size | Full file | Optimal lines | Optimal rules | Optimal size | Optimal file | Minimal lines | Minimal rules | Minimal size | Minimal file |
| --- | ---: | ---: | ---: | --- | ---: | ---: | ---: | --- | ---: | ---: | ---: | --- |
| A Philosophy of Software Design | 320 | 151 | 10454 B | [full](a-philosophy-of-software-design/a-philosophy-of-software-design.md) | 34 | 16 | 2169 B | [optimal](a-philosophy-of-software-design/a-philosophy-of-software-design.optimal.md) | 29 | 11 | 1032 B | [minimal](a-philosophy-of-software-design/a-philosophy-of-software-design.minimal.md) |
| Clean Architecture | 471 | 226 | 14355 B | [full](clean-architecture/clean-architecture.md) | 34 | 16 | 2194 B | [optimal](clean-architecture/clean-architecture.optimal.md) | 29 | 11 | 934 B | [minimal](clean-architecture/clean-architecture.minimal.md) |
| Clean Code | 246 | 173 | 10595 B | [full](clean-code/clean-code.md) | 34 | 16 | 2150 B | [optimal](clean-code/clean-code.optimal.md) | 29 | 11 | 856 B | [minimal](clean-code/clean-code.minimal.md) |
| Code Complete | 288 | 144 | 8563 B | [full](code-complete/code-complete.md) | 33 | 15 | 1709 B | [optimal](code-complete/code-complete.optimal.md) | 29 | 11 | 777 B | [minimal](code-complete/code-complete.minimal.md) |
| Designing Data-Intensive Applications | 307 | 152 | 9951 B | [full](designing-data-intensive-applications/designing-data-intensive-applications.md) | 33 | 15 | 2090 B | [optimal](designing-data-intensive-applications/designing-data-intensive-applications.optimal.md) | 29 | 11 | 880 B | [minimal](designing-data-intensive-applications/designing-data-intensive-applications.minimal.md) |
| Domain-Driven Design | 986 | 517 | 38304 B | [full](domain-driven-design/domain-driven-design.md) | 34 | 16 | 2210 B | [optimal](domain-driven-design/domain-driven-design.optimal.md) | 30 | 12 | 1024 B | [minimal](domain-driven-design/domain-driven-design.minimal.md) |
| Domain-Driven Design Distilled | 283 | 136 | 8388 B | [full](domain-driven-design-distilled/domain-driven-design-distilled.md) | 34 | 16 | 1811 B | [optimal](domain-driven-design-distilled/domain-driven-design-distilled.optimal.md) | 29 | 11 | 818 B | [minimal](domain-driven-design-distilled/domain-driven-design-distilled.minimal.md) |
| Implementing Domain-Driven Design | 316 | 164 | 11249 B | [full](implementing-domain-driven-design/implementing-domain-driven-design.md) | 34 | 16 | 2040 B | [optimal](implementing-domain-driven-design/implementing-domain-driven-design.optimal.md) | 29 | 11 | 1001 B | [minimal](implementing-domain-driven-design/implementing-domain-driven-design.minimal.md) |
| Patterns of Enterprise Application Architecture | 354 | 160 | 11192 B | [full](patterns-of-enterprise-application-architecture/patterns-of-enterprise-application-architecture.md) | 33 | 15 | 1971 B | [optimal](patterns-of-enterprise-application-architecture/patterns-of-enterprise-application-architecture.optimal.md) | 29 | 11 | 957 B | [minimal](patterns-of-enterprise-application-architecture/patterns-of-enterprise-application-architecture.minimal.md) |
| Refactoring | 366 | 177 | 12812 B | [full](refactoring/refactoring.md) | 33 | 15 | 1859 B | [optimal](refactoring/refactoring.optimal.md) | 29 | 11 | 700 B | [minimal](refactoring/refactoring.minimal.md) |
| Release It! | 343 | 176 | 10147 B | [full](release-it/release-it.md) | 34 | 16 | 1672 B | [optimal](release-it/release-it.optimal.md) | 30 | 12 | 878 B | [minimal](release-it/release-it.minimal.md) |
| The Pragmatic Programmer | 303 | 142 | 9572 B | [full](the-pragmatic-programmer/the-pragmatic-programmer.md) | 33 | 15 | 1628 B | [optimal](the-pragmatic-programmer/the-pragmatic-programmer.optimal.md) | 29 | 11 | 770 B | [minimal](the-pragmatic-programmer/the-pragmatic-programmer.minimal.md) |
| Working Effectively with Legacy Code | 331 | 157 | 10497 B | [full](working-effectively-with-legacy-code/working-effectively-with-legacy-code.md) | 33 | 15 | 1718 B | [optimal](working-effectively-with-legacy-code/working-effectively-with-legacy-code.optimal.md) | 29 | 11 | 878 B | [minimal](working-effectively-with-legacy-code/working-effectively-with-legacy-code.minimal.md) |

## Books

### A Philosophy of Software Design

Author: John Ousterhout

The book focuses on fighting complexity through deep modules, simple interfaces, information hiding, and design choices that reduce cognitive load. This rule set is especially useful for API design, module design, and refactoring shallow abstractions.

### Clean Architecture

Author: Robert C. Martin

The book describes designing systems around stable boundaries, the dependency rule, and the separation of business policies from details such as frameworks, databases, and UI. This rule set helps keep code resistant to technology churn.

### Clean Code

Author: Robert C. Martin

The book focuses on readability, naming, small functions, responsibilities, tests, and simplicity. This rule set is a strong default for everyday coding and code review.

### Code Complete

Author: Steve McConnell

The book covers a broad range of software construction practices: routine design, variables, classes, control flow, defensive programming, coding standards, and testing. This rule set helps agents make disciplined implementation decisions.

### Designing Data-Intensive Applications

Author: Martin Kleppmann

The book covers reliability, scalability, consistency, replication, partitioning, transactions, data streams, and schema evolution. This rule set is intended for systems where data ownership, event flows, and consistency semantics matter.

### Domain-Driven Design

Author: Eric Evans

The book introduces domain modeling, ubiquitous language, bounded contexts, tactical patterns, and strategic design. This rule set helps agents think in terms of the business model rather than tables, controllers, or DTOs.

### Domain-Driven Design Distilled

Author: Vaughn Vernon

The book is a short, practical introduction to DDD. It focuses on subdomains, bounded contexts, context mapping, and basic tactical patterns. This rule set is a good fit when you want the benefits of DDD without excessive ceremony.

### Implementing Domain-Driven Design

Author: Vaughn Vernon

The book shows how to apply DDD in real systems: aggregates, domain events, contexts, integrations, and application architecture. This rule set is more implementation-focused than `domain-driven-design-distilled`.

### Patterns of Enterprise Application Architecture

Author: Martin Fowler

The book catalogues enterprise application patterns: layers, service layer, transaction script, domain model, data mapper, repository, unit of work, identity map, DTO, and integration patterns. This rule set helps choose an appropriate pattern instead of mixing responsibilities accidentally.

### Refactoring

Author: Martin Fowler

The book describes safe ways to improve code structure without changing observable behavior. This rule set emphasizes small steps, tests, code smell detection, and keeping refactoring separate from feature changes.

### Release It!

Author: Michael T. Nygard

The book focuses on systems that survive production reality: failures, overload, timeouts, retries, circuit breakers, bulkheads, backpressure, observability, and deployment behavior. This rule set is useful for services, APIs, queues, integrations, and critical production paths.

### The Pragmatic Programmer

Authors: Andrew Hunt, David Thomas

The book describes a pragmatic approach to software development: responsibility, DRY at the knowledge level, orthogonality, automation, fast feedback, prototyping, and adaptability. This rule set works well as a general engineering layer.

### Working Effectively with Legacy Code

Author: Michael Feathers

The book explains how to safely change difficult, poorly tested code: characterization tests, seams, dependency breaking, sprout method, wrap method, and incremental risk reduction. This rule set is best for legacy work where the first goal is regaining control.

## Choosing Rules

For criticism and caveats about combining rule sets, see [CRITICISM.md](CRITICISM.md).

Choose rules based on the task:

- everyday code quality: `clean-code`, `code-complete`
- architecture and boundaries: `clean-architecture`, `domain-driven-design`, `patterns-of-enterprise-application-architecture`
- domain modeling: `domain-driven-design`, `domain-driven-design-distilled`, `implementing-domain-driven-design`
- refactoring: `refactoring`, `a-philosophy-of-software-design`
- legacy code: `working-effectively-with-legacy-code`, optionally `refactoring`
- production systems: `release-it`
- data systems: `designing-data-intensive-applications`
- general engineering style: `clean-code`, `code-complete`, `the-pragmatic-programmer`

## Constructive criticism from Reddit

Below is a consolidated list of recurring criticisms and suggestions from the Reddit discussion, ordered from the most valid to the least valid.

### 1. There is no clear measurement of improvement

**Validity: 9/10**

This is the strongest criticism. Without benchmarks, before/after comparisons, defect counts, review effort, or task-completion data, it is hard to know whether the rules actually improve code quality or just feel useful.

### 2. This can burn tokens and pollute the context

**Validity: 9/10**

Many of the generated rule files contain a large number of individual instructions. Loading too many of them at once can increase token usage, crowd out task-specific context, and make the agent less focused.

### 3. Skills, RAG, or progressive loading may be better than putting everything into `AGENTS.md`

**Validity: 9/10**

The rules are likely more useful when loaded selectively. Refactoring rules should be used during refactoring, legacy-code rules when working with legacy systems, data-intensive design rules when working on data-heavy systems, and so on.

### 4. A short set of project-specific rules may work better

**Validity: 9/10**

A compact `AGENTS.md` with 10–15 strong, testable, project-specific instructions may be more effective in daily use than a large generic rule set distilled from books.

### 5. The model may ignore many of the rules anyway

**Validity: 8/10**

LLMs do not reliably obey hundreds of instructions at the same time. More rules can increase coverage, but they can also create ambiguity, competition between instructions, and instruction fatigue.

### 6. Rules should also come from real project failures

**Validity: 8/10**

Book-derived rules are a useful starting point, but the most valuable agent rules are often based on actual incidents: the agent made a mistake, it caused a specific problem, and a new rule was added to prevent it from happening again.

### 7. Rules from different books may conflict

**Validity: 8/10**

Different books operate at different abstraction levels and sometimes encourage different tradeoffs. For example, rules inspired by Clean Code, Clean Architecture, DDD, DDIA, PoEAA, and A Philosophy of Software Design may push the agent toward different architectural decisions.

### 8. The approach may cause overengineering

**Validity: 8/10**

If the agent applies heavyweight architecture rules to a small feature or simple CRUD task, it may introduce unnecessary layers, abstractions, factories, ports, adapters, aggregates, or domain events.

### 9. The project could include more AI-agent-specific material

**Validity: 7/10**

Software engineering books teach good design, but AI coding agents also need operational guidance: tool use, planning loops, verification, test execution, avoiding guesses, scoped edits, and recovery from failed runs.

### 10. Too many abstract rules may lead to pseudo-compliance

**Validity: 7/10**

The agent may produce code that appears architecturally “proper” while still missing the actual task constraints. The risk is not that the rules are wrong, but that they may encourage surface-level compliance instead of practical correctness.

### 11. There may be legal or licensing concerns

**Validity: 6/10**

This is potentially important, but difficult to evaluate without legal analysis. A safer framing is that the project contains practical, original agent instructions inspired by software engineering principles, not substitutes for the books themselves. But... it's a destilled content taken from ChatGPT. So OpenAI had stolen books, I distilled ChatGPT, will OpenAI sue me for this?

### 12. The LLM may already know these books

**Validity: 5/10**

This is partly true, but incomplete. Models may know the principles, yet still fail to apply them consistently. Explicit context can help, but a full book-sized rule set is not automatically better than a short, targeted reminder.

### 13. Some principles may be outdated in the AI coding era

**Validity: 5/10**

AI changes the economics of writing, rewriting, and refactoring code. However, many core principles remain relevant: readability, modularity, testability, resilience, boundaries, and maintainability.

## Adding a Book

Use lowercase kebab-case for the book directory name.

Workflow:

1. Ask the chatbot for the book and every chapter in it. Then ask it to expand the chapter list with all sections. Then ask it to expand the section list with all rules contained in each section.
2. Ask the chatbot to produce an `AGENTS.md` file that expresses the entire content as rules for AI agents.
3. Move that file to `_rule-workbench/<book-name>/full.md`.
4. Ask the chatbot to run the workflow from [_rule-workbench/PROCESS.md](/Users/maciej/Projects/AGENTS/_rule-workbench/PROCESS.md:1) for that book.
5. Ask the chatbot to execute the release instructions from [_rule-workbench/RELEASE.md](/Users/maciej/Projects/AGENTS/_rule-workbench/RELEASE.md:1).

## Important Note

These rules are inspired by the books listed above. They are not official materials from the authors or publishers, and they are not a substitute for reading the books.

The files in this repository are practical engineering instructions written for AI coding tools. They intentionally avoid reproducing book text. Use them as lightweight working agreements, not as summaries or study notes.

## License

The code and rules in this repository are released under the MIT License.

See [LICENSE](LICENSE) for details.

## Author

[Maciej Ciemborowicz](https://maciej-ciemborowicz.eu)
