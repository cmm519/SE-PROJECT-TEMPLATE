# How to use agent-rules-books

Local copy of [ciembor/agent-rules-books](https://github.com/ciembor/agent-rules-books) (MIT). These are decision rules inspired by software books. They are not the books, and they are not your architecture, your goals, or your context.

Folder: `user resources/agent-rules-books/`

## What to load

| Version | Use when |
| --- | --- |
| `*.mini.md` | The one file this template will read during implementation |
| `*.nano.md` | A smaller always-on baseline, if you later install rules yourself |
| full `*.md` | A deep audit, not a normal session |
| `SKILL.md` | Entrypoint that points at the mini set |

Load one book. Pairs that conflict are listed in `agent-rules-books/docs/COMPATIBILITY.md`.

## Use with this template

1. Fill `context.template.md`, `goals.template.md`, `architecture.template.md`, `structure.template.md`, and `method.template.md`.
2. In `architecture.template.md`, set **Primary design rule** to one `*.mini.md` path, or to `none`.
3. `AGENT-PROMPT.md` reads that one file while it writes code. It does not paste the book into `progress.md`, and it does not open a second book.

Examples:

- Everyday readability → `clean-code/clean-code.mini.md`
- Behavior-preserving restructure → `refactoring/refactoring.mini.md`
- Fragile or hard-to-test code → `working-effectively-with-legacy-code/working-effectively-with-legacy-code.mini.md`
- Dependency direction → `clean-architecture/clean-architecture.mini.md`
- Domain language → `domain-driven-design-distilled/domain-driven-design-distilled.mini.md`

These files stay under `user resources/`. You do not need to copy them into `.cursor/` for this workflow.

## More detail

- Book list: `agent-rules-books/README.md`
- Editor setup: `agent-rules-books/docs/USAGE.md`
- Why this is not the architecture plan: `../METHODS.md`

Upstream: https://github.com/ciembor/agent-rules-books
