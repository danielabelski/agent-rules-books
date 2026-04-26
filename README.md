# AGENTS Book Rules

![AGENTS Book Rules](books-ai-rules.png)

MIT licensed universal project rules for coding agents.

This repository contains ready-to-use rule sets inspired by well-known books on software design, architecture, refactoring, legacy code, reliability, and data-intensive systems.

For constructive criticism from Reddit, see [CRITICISM.md](CRITICISM.md).
For editor-specific setup in Codex, Claude Code, and Cursor, see [USAGE.md](USAGE.md). It covers always-on vs on-demand usage, skills, scoped rules, MCP or RAG patterns, and the preferred setup for each editor.

Each rule set is released in three tool-agnostic Markdown versions:

- `full`: the canonical complete source
- `min`: the compressed on-demand version
- `nano`: the compressed always-on version for tight context budgets

## Quick Start

- start with one primary rule set in `nano`
- open [USAGE.md](USAGE.md) and follow the setup for Codex, Claude Code, or Cursor
- keep `nano` as the always-on base layer
- switch to `min` only when the task needs more book-specific pressure
- use `full` for reference, audits, or for deriving narrower scoped rules or skills
- avoid loading every rule at once

## Release Matrix

Metrics:

- `lines`: physical line count from `wc -l`
- `rules`: Markdown list items counted with the deterministic release convention
- `size`: raw bytes from `wc -c`

| Rule Set | Full lines | Full rules | Full size | Full file | Min lines | Min rules | Min size | Min file | Nano lines | Nano rules | Nano size | Nano file |
| --- | ---: | ---: | ---: | --- | ---: | ---: | ---: | --- | ---: | ---: | ---: | --- |
| [A Philosophy of Software Design](a-philosophy-of-software-design/) | 320 | 151 | 10454 B | [full](a-philosophy-of-software-design/a-philosophy-of-software-design.md) | 34 | 16 | 2165 B | [min](a-philosophy-of-software-design/a-philosophy-of-software-design.min.md) | 29 | 11 | 1029 B | [nano](a-philosophy-of-software-design/a-philosophy-of-software-design.nano.md) |
| [Clean Architecture](clean-architecture/) | 471 | 226 | 14355 B | [full](clean-architecture/clean-architecture.md) | 34 | 16 | 2190 B | [min](clean-architecture/clean-architecture.min.md) | 29 | 11 | 931 B | [nano](clean-architecture/clean-architecture.nano.md) |
| [Clean Code](clean-code/) | 246 | 173 | 10595 B | [full](clean-code/clean-code.md) | 34 | 16 | 2146 B | [min](clean-code/clean-code.min.md) | 29 | 11 | 853 B | [nano](clean-code/clean-code.nano.md) |
| [Code Complete](code-complete/) | 288 | 144 | 8563 B | [full](code-complete/code-complete.md) | 33 | 15 | 1705 B | [min](code-complete/code-complete.min.md) | 29 | 11 | 774 B | [nano](code-complete/code-complete.nano.md) |
| [Designing Data-Intensive Applications](designing-data-intensive-applications/) | 307 | 152 | 9951 B | [full](designing-data-intensive-applications/designing-data-intensive-applications.md) | 33 | 15 | 2086 B | [min](designing-data-intensive-applications/designing-data-intensive-applications.min.md) | 29 | 11 | 877 B | [nano](designing-data-intensive-applications/designing-data-intensive-applications.nano.md) |
| [Domain-Driven Design](domain-driven-design/) | 986 | 517 | 38304 B | [full](domain-driven-design/domain-driven-design.md) | 34 | 16 | 2206 B | [min](domain-driven-design/domain-driven-design.min.md) | 30 | 12 | 1021 B | [nano](domain-driven-design/domain-driven-design.nano.md) |
| [Domain-Driven Design Distilled](domain-driven-design-distilled/) | 283 | 136 | 8388 B | [full](domain-driven-design-distilled/domain-driven-design-distilled.md) | 34 | 16 | 1807 B | [min](domain-driven-design-distilled/domain-driven-design-distilled.min.md) | 29 | 11 | 815 B | [nano](domain-driven-design-distilled/domain-driven-design-distilled.nano.md) |
| [Implementing Domain-Driven Design](implementing-domain-driven-design/) | 316 | 164 | 11249 B | [full](implementing-domain-driven-design/implementing-domain-driven-design.md) | 34 | 16 | 2036 B | [min](implementing-domain-driven-design/implementing-domain-driven-design.min.md) | 29 | 11 | 998 B | [nano](implementing-domain-driven-design/implementing-domain-driven-design.nano.md) |
| [Patterns of Enterprise Application Architecture](patterns-of-enterprise-application-architecture/) | 354 | 160 | 11192 B | [full](patterns-of-enterprise-application-architecture/patterns-of-enterprise-application-architecture.md) | 33 | 15 | 1967 B | [min](patterns-of-enterprise-application-architecture/patterns-of-enterprise-application-architecture.min.md) | 29 | 11 | 954 B | [nano](patterns-of-enterprise-application-architecture/patterns-of-enterprise-application-architecture.nano.md) |
| [Refactoring](refactoring/) | 366 | 177 | 12812 B | [full](refactoring/refactoring.md) | 33 | 15 | 1855 B | [min](refactoring/refactoring.min.md) | 29 | 11 | 697 B | [nano](refactoring/refactoring.nano.md) |
| [Release It!](release-it/) | 343 | 176 | 10147 B | [full](release-it/release-it.md) | 34 | 16 | 1668 B | [min](release-it/release-it.min.md) | 30 | 12 | 875 B | [nano](release-it/release-it.nano.md) |
| [The Pragmatic Programmer](the-pragmatic-programmer/) | 303 | 142 | 9572 B | [full](the-pragmatic-programmer/the-pragmatic-programmer.md) | 33 | 15 | 1624 B | [min](the-pragmatic-programmer/the-pragmatic-programmer.min.md) | 29 | 11 | 767 B | [nano](the-pragmatic-programmer/the-pragmatic-programmer.nano.md) |
| [Working Effectively with Legacy Code](working-effectively-with-legacy-code/) | 331 | 157 | 10497 B | [full](working-effectively-with-legacy-code/working-effectively-with-legacy-code.md) | 33 | 15 | 1714 B | [min](working-effectively-with-legacy-code/working-effectively-with-legacy-code.min.md) | 29 | 11 | 875 B | [nano](working-effectively-with-legacy-code/working-effectively-with-legacy-code.nano.md) |

## Books

### [A Philosophy of Software Design](https://www.goodreads.com/book/show/39996759-a-philosophy-of-software-design)

Author: [John Ousterhout](https://web.stanford.edu/~ouster/cgi-bin/home.php)

The book focuses on fighting complexity through deep modules, simple interfaces, information hiding, and design choices that reduce cognitive load. This rule set is especially useful for API design, module design, and refactoring shallow abstractions.

### [Clean Architecture](https://www.goodreads.com/book/show/18043011-clean-architecture)

Author: [Robert C. Martin](https://cleancoder.com/)

The book describes designing systems around stable boundaries, the dependency rule, and the separation of business policies from details such as frameworks, databases, and UI. This rule set helps keep code resistant to technology churn.

### [Clean Code](https://www.goodreads.com/book/show/3735293-clean-code)

Author: [Robert C. Martin](https://cleancoder.com/)

The book focuses on readability, naming, small functions, responsibilities, tests, and simplicity. This rule set is a strong default for everyday coding and code review.

### [Code Complete](https://www.goodreads.com/book/show/4845.Code_Complete)

Author: [Steve McConnell](https://www.construx.com/about-us/our-experts/steve-mcconnell/)

The book covers a broad range of software construction practices: routine design, variables, classes, control flow, defensive programming, coding standards, and testing. This rule set helps agents make disciplined implementation decisions.

### [Designing Data-Intensive Applications](https://www.goodreads.com/book/show/23463279-designing-data-intensive-applications)

Author: [Martin Kleppmann](https://martin.kleppmann.com/)

The book covers reliability, scalability, consistency, replication, partitioning, transactions, data streams, and schema evolution. This rule set is intended for systems where data ownership, event flows, and consistency semantics matter.

### [Domain-Driven Design](https://www.goodreads.com/en/book/show/179133)

Author: [Eric Evans](https://domainlanguage.com/)

The book introduces domain modeling, ubiquitous language, bounded contexts, tactical patterns, and strategic design. This rule set helps agents think in terms of the business model rather than tables, controllers, or DTOs.

### [Domain-Driven Design Distilled](https://www.goodreads.com/book/show/28602719-domain-driven-design-distilled)

Author: [Vaughn Vernon](https://vaughnvernon.com/)

The book is a short, practical introduction to DDD. It focuses on subdomains, bounded contexts, context mapping, and basic tactical patterns. This rule set is a good fit when you want the benefits of DDD without excessive ceremony.

### [Implementing Domain-Driven Design](https://www.goodreads.com/book/show/18396266-implementing-domain-driven-design)

Author: [Vaughn Vernon](https://vaughnvernon.com/)

The book shows how to apply DDD in real systems: aggregates, domain events, contexts, integrations, and application architecture. This rule set is more implementation-focused than `domain-driven-design-distilled`.

### [Patterns of Enterprise Application Architecture](https://www.goodreads.com/en/book/show/70156.Patterns_of_Enterprise_Application_Architecture)

Author: [Martin Fowler](https://martinfowler.com/)

The book catalogues enterprise application patterns: layers, service layer, transaction script, domain model, data mapper, repository, unit of work, identity map, DTO, and integration patterns. This rule set helps choose an appropriate pattern instead of mixing responsibilities accidentally.

### [Refactoring](https://www.goodreads.com/book/show/44936.Refactoring)

Author: [Martin Fowler](https://martinfowler.com/)

The book describes safe ways to improve code structure without changing observable behavior. This rule set emphasizes small steps, tests, code smell detection, and keeping refactoring separate from feature changes.

### [Release It!](https://www.goodreads.com/en/book/show/1069827.Release_It_)

Author: [Michael T. Nygard](https://www.michaelnygard.com/)

The book focuses on systems that survive production reality: failures, overload, timeouts, retries, circuit breakers, bulkheads, backpressure, observability, and deployment behavior. This rule set is useful for services, APIs, queues, integrations, and critical production paths.

### [The Pragmatic Programmer](https://www.goodreads.com/book/show/50701156)

Authors: [Andrew Hunt](https://toolshed.com/), [David Thomas](https://pragdave.me/)

The book describes a pragmatic approach to software development: responsibility, DRY at the knowledge level, orthogonality, automation, fast feedback, prototyping, and adaptability. This rule set works well as a general engineering layer.

### [Working Effectively with Legacy Code](https://www.goodreads.com/book/show/44919.Working_Effectively_with_Legacy_Code)

Author: [Michael Feathers](https://www.r7krecon.com/)

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
