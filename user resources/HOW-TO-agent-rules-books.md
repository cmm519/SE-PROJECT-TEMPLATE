# How to use agent-rules-books (MoT / Cursor)

Local copy of [ciembor/agent-rules-books](https://github.com/ciembor/agent-rules-books) (MIT). These are **AGENTS.md-style rules and skills** inspired by classic software books. They are not the books themselves and are not a substitute for reading them.

Folder: `user resources/agent-rules-books/`

These files are implementation bias. They are not your architecture and not your SRS. Read [ARCHITECTURE-NOTES.md](ARCHITECTURE-NOTES.md) before choosing one.

## What to load

Each book folder has three rule sizes plus a `SKILL.md` entrypoint:

| Version | Use when |
| --- | --- |
| `*.mini.md` | Default for real Cursor tasks (recommended) |
| `*.nano.md` | Very tight always-on / portable baselines |
| full `*.md` | Deep reference, audits, or one-off deep sessions |
| `SKILL.md` | Skill entrypoint that points at the mini set |

Prefer **one primary book** per session so rules do not fight each other. The compatibility matrix is `agent-rules-books/docs/COMPATIBILITY.md`.

## Use with this MoT workflow

1. Fill `srs.template.md`, `architecture.template.md`, and `structure.template.md` as described in the root `README.md`.
2. In `architecture.template.md`, set **Primary design rule** to one `*.mini.md` path, or to `none`.
3. Stage 4 (the prompt generator) does not paste that file into the increments.
4. Stage 6 (the implementation guide) reads that one path while it writes code. It does not open a second book.

Examples of when to pick which set:

- Everyday coding / readability → `clean-code/clean-code.mini.md`
- Restructure without changing behavior → `refactoring/refactoring.mini.md`
- Hard-to-test or fragile code → `working-effectively-with-legacy-code/working-effectively-with-legacy-code.mini.md`
- Boundaries and dependency direction → `clean-architecture/clean-architecture.mini.md`
- Domain modeling → `domain-driven-design-distilled/domain-driven-design-distilled.mini.md` (lighter) or `domain-driven-design/domain-driven-design.mini.md`

These files stay under `user resources/` as portable reference. You do not need to install them into `.cursor/` for the MoT flow.

## Optional later: Cursor project rules or skills

When you build a real app from this template and want a lasting bias:

- Copy one `*.mini.md` into `.cursor/rules` as a scoped or manual rule, or
- Use that book's `SKILL.md` pattern under `.cursor/skills` / `.agents/skills`

Do not paste several `full` files into Always Apply rules.

## More detail

- Overview and book list: `agent-rules-books/README.md`
- Editor patterns (Cursor, Codex, Claude Code): `agent-rules-books/docs/USAGE.md`

Upstream: https://github.com/ciembor/agent-rules-books
