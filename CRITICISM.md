# Constructive criticism from Reddit

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
