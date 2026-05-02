<h1>
  📚 AGENTS Book Rules
  <a href="CHANGELOG.md"><img align="right" src="https://img.shields.io/badge/version-v0.2-blue?style=for-the-badge" alt="Version v0.2" height="32"></a>
</h1>

![AGENTS Book Rules](books-ai-rules.png)

MIT licensed universal project rules for coding agents.

This repository contains ready-to-use rule sets inspired by well-known books on software design, architecture, refactoring, legacy code, reliability, and data-intensive systems.

For editor-specific setup in Codex, Claude Code, and Cursor, see [USAGE.md](USAGE.md). It covers always-on vs on-demand usage, skills, scoped rules, MCP or RAG patterns, and the preferred setup for each editor.

Each rule set is released in three tool-agnostic Markdown versions:

- `mini`: the recommended version for most real task use
- `nano`: the compact fallback for very tight context budgets
- `full`: the canonical complete source and reference version

For constructive criticism from Reddit, see [CRITICISM.md](CRITICISM.md).

For release history, see [CHANGELOG.md](CHANGELOG.md).

## Release Matrix

Metrics:

- `lines`: physical line count from `wc -l`
- `rules`: Markdown list items counted with the deterministic release convention
- `size`: raw bytes from `wc -c`

| Rule Set | Full file | Full lines | Full rules | Full size | Mini file | Mini lines | Mini rules | Mini size | Nano file | Nano lines | Nano rules | Nano size |
| --- | --- | ---: | ---: | ---: | --- | ---: | ---: | ---: | --- | ---: | ---: | ---: |
| [A Philosophy of Software Design](a-philosophy-of-software-design/) | [full](a-philosophy-of-software-design/a-philosophy-of-software-design.md) | 370 | 177 | 13537 B | [mini](a-philosophy-of-software-design/a-philosophy-of-software-design.mini.md) | 46 | 28 | 5756 B | [nano](a-philosophy-of-software-design/a-philosophy-of-software-design.nano.md) | 35 | 17 | 2240 B |
| [Clean Architecture](clean-architecture/) | [full](clean-architecture/clean-architecture.md) | 515 | 289 | 17757 B | [mini](clean-architecture/clean-architecture.mini.md) | 49 | 31 | 5467 B | [nano](clean-architecture/clean-architecture.nano.md) | 36 | 18 | 2235 B |
| [Clean Code](clean-code/) | [full](clean-code/clean-code.md) | 297 | 220 | 13826 B | [mini](clean-code/clean-code.mini.md) | 47 | 29 | 3785 B | [nano](clean-code/clean-code.nano.md) | 32 | 14 | 1216 B |
| [Code Complete](code-complete/) | [full](code-complete/code-complete.md) | 354 | 180 | 12383 B | [mini](code-complete/code-complete.mini.md) | 56 | 38 | 6699 B | [nano](code-complete/code-complete.nano.md) | 41 | 23 | 2526 B |
| [Designing Data-Intensive Applications](designing-data-intensive-applications/) | [full](designing-data-intensive-applications/designing-data-intensive-applications.md) | 393 | 205 | 16059 B | [mini](designing-data-intensive-applications/designing-data-intensive-applications.mini.md) | 55 | 37 | 6930 B | [nano](designing-data-intensive-applications/designing-data-intensive-applications.nano.md) | 34 | 16 | 2556 B |
| [Domain-Driven Design](domain-driven-design/) | [full](domain-driven-design/domain-driven-design.md) | 979 | 523 | 42405 B | [mini](domain-driven-design/domain-driven-design.mini.md) | 48 | 30 | 5670 B | [nano](domain-driven-design/domain-driven-design.nano.md) | 39 | 21 | 2253 B |
| [Domain-Driven Design Distilled](domain-driven-design-distilled/) | [full](domain-driven-design-distilled/domain-driven-design-distilled.md) | 317 | 158 | 11329 B | [mini](domain-driven-design-distilled/domain-driven-design-distilled.mini.md) | 56 | 38 | 6422 B | [nano](domain-driven-design-distilled/domain-driven-design-distilled.nano.md) | 41 | 23 | 2519 B |
| [Implementing Domain-Driven Design](implementing-domain-driven-design/) | [full](implementing-domain-driven-design/implementing-domain-driven-design.md) | 337 | 177 | 12826 B | [mini](implementing-domain-driven-design/implementing-domain-driven-design.mini.md) | 57 | 39 | 7317 B | [nano](implementing-domain-driven-design/implementing-domain-driven-design.nano.md) | 37 | 19 | 2707 B |
| [Patterns of Enterprise Application Architecture](patterns-of-enterprise-application-architecture/) | [full](patterns-of-enterprise-application-architecture/patterns-of-enterprise-application-architecture.md) | 404 | 196 | 15479 B | [mini](patterns-of-enterprise-application-architecture/patterns-of-enterprise-application-architecture.mini.md) | 54 | 36 | 8083 B | [nano](patterns-of-enterprise-application-architecture/patterns-of-enterprise-application-architecture.nano.md) | 35 | 17 | 2807 B |
| [Refactoring](refactoring/) | [full](refactoring/refactoring.md) | 433 | 242 | 17844 B | [mini](refactoring/refactoring.mini.md) | 49 | 31 | 5151 B | [nano](refactoring/refactoring.nano.md) | 37 | 19 | 1970 B |
| [Release It!](release-it/) | [full](release-it/release-it.md) | 382 | 204 | 13516 B | [mini](release-it/release-it.mini.md) | 48 | 30 | 6352 B | [nano](release-it/release-it.nano.md) | 38 | 20 | 2185 B |
| [The Pragmatic Programmer](the-pragmatic-programmer/) | [full](the-pragmatic-programmer/the-pragmatic-programmer.md) | 359 | 179 | 13361 B | [mini](the-pragmatic-programmer/the-pragmatic-programmer.mini.md) | 65 | 47 | 7134 B | [nano](the-pragmatic-programmer/the-pragmatic-programmer.nano.md) | 44 | 26 | 2232 B |
| [Working Effectively with Legacy Code](working-effectively-with-legacy-code/) | [full](working-effectively-with-legacy-code/working-effectively-with-legacy-code.md) | 371 | 193 | 13792 B | [mini](working-effectively-with-legacy-code/working-effectively-with-legacy-code.mini.md) | 50 | 32 | 5688 B | [nano](working-effectively-with-legacy-code/working-effectively-with-legacy-code.nano.md) | 35 | 17 | 1773 B |

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

1. Ask the chatbot for the complete book outline: every chapter, every section inside each chapter, and every operational rule stated or strongly implied by each section.
2. Ask the chatbot to expand the extraction until nothing material is missing. In particular, recover non-negotiable rules, tradeoff rules, trigger rules, anti-patterns, review and testing guidance, and any “when uncertain” guidance.
3. Ask the chatbot to produce a full `AGENTS.md` in this repository's `full` standard, not a loose summary. It should preserve the book's structure and distinctive bias, express obligations as `MUST`, strong defaults as `SHOULD`, prohibitions as `MUST NOT`, and keep anti-patterns explicit.
4. Review the generated `AGENTS.md` before importing it. Check that no important local discipline was flattened into generic advice, that modal strength matches the book's intent, and that the chatbot did not invent unsupported rules.
5. Move the approved file to `_rule-workbench/<book-name>/full.md`.
6. Ask the chatbot to run the workflow from [_rule-workbench/PROCESS.md](/Users/maciej/Projects/AGENTS/_rule-workbench/PROCESS.md:1) for that book.
7. Ask the chatbot to execute the release instructions from [_rule-workbench/RELEASE.md](/Users/maciej/Projects/AGENTS/_rule-workbench/RELEASE.md:1).

## Important Note

These rules are inspired by the books listed above. They are not official materials from the authors or publishers, and they are not a substitute for reading the books.

The files in this repository are practical engineering instructions written for AI coding tools. They intentionally avoid reproducing book text. Use them as lightweight working agreements, not as summaries or study notes.

## License

The code and rules in this repository are released under the MIT License.

See [LICENSE](LICENSE) for details.

## Author

[Maciej Ciemborowicz](https://maciej-ciemborowicz.eu)
