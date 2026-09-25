# Architecture notes for this template

This note answers one question: are the files in `agent-rules-books/` a good architecture plan for agents?

## Verdict

**Yes, as coding decision rules. No, as the architecture plan.**

`agent-rules-books/` is a local copy of [ciembor/agent-rules-books](https://github.com/ciembor/agent-rules-books) (MIT). Each book has a short `mini` file, a smaller `nano` file, a long `full` file, and a `SKILL.md`. The `mini` files are the ones worth loading. Clean Architecture's mini file, for example, is a short set of decisions: dependencies point inward, business rules stay free of frameworks, adapters stay humble.

The pack already says how not to misuse it. `agent-rules-books/docs/USAGE.md` says to load the smallest set that changes a decision. `agent-rules-books/docs/COMPATIBILITY.md` says not to load conflicting pairs together (domain-driven design against Patterns of Enterprise Application Architecture) and to pick one primary book when two sets overlap. Upstream criticism in `agent-rules-books/docs/CRITICISM.md` still holds: there are no measured coding outcomes, and loading several full files crowds out the task.

None of those files describe your system. They do not name your users, your parts, your requirement IDs, or your directory tree. They do not replace an SRS or a diagram.

## What an agent should use as the plan

You write the plan. The agent reads it.

| Question | File you fill | What the agent is allowed to do |
| --- | --- | --- |
| What must the software do? | `srs.template.md` | Cite IDs. Not invent requirements |
| What are the parts and the decisions? | `architecture.template.md` | Stay inside the parts and decisions. Not invent a second architecture |
| Where do the files go, and how do they build? | `structure.template.md` | Use those paths and commands |

`architecture.template.md` is a small C4-style plan: a context diagram, a container diagram, a part list, and one to three decisions (context, decision, rejected alternative). That is enough for a later session to reload. A full arc42 document or the whole of ISO/IEC/IEEE 42010 is more than this starter should inject into every chat.

The book rule is optional and late. If you set **Primary design rule** to one `*.mini.md` path, the implementation session reads that file while writing code inside the boundaries you already named. The prompt generator does not copy it into every increment.

## What not to do

- Do not attach several book files "so the agent has more design standards."
- Do not treat a book mini file as the system architecture.
- Do not skip `architecture.template.md` because the book folder exists.
