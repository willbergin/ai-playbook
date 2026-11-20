# AI setup

I keep the agent instructions, skills and prompts I reuse across projects here. The delivery playbook is the main workflow. It takes a scoped issue through implementation, independent review and, when requested, production release.

## What’s in here

| File or folder | What it’s for |
| --- | --- |
| [workflow.md](workflow.md) | How an issue moves through the stages, with an example and a skill index |
| [agents/lead.md](agents/lead.md), [builder.md](agents/builder.md), [reviewer.md](agents/reviewer.md) | Who owns each stage and what they pass on |
| [Skill index](workflow.md#skills-to-use-as-needed) | Procedures for repeatable tasks, from capturing an issue to verifying a preview |
| [Prompt index](workflow.md#prompts-and-templates) | Templates to paste into a session or attach to an issue or change request |
| [config/setup.md](config/setup.md) | Install the playbook, configure a project and start a run |
| [examples/practice-run.md](examples/practice-run.md) | Try the review and handoff without live accounts |

## How a run works

1. **Lead** takes an idea or existing issue and makes sure the outcome and acceptance criteria are clear.
2. **Builder** implements the change and hands over the change request, candidate commit, checks and preview.
3. **Reviewer** uses those records to test the acceptance criteria. If the Builder pushes a fix, the new commit needs fresh review.
4. **Lead** coordinates an approved release, checks production and updates the issue when authorised.

A request to take an issue to a verified preview ends after step 3. See the [workflow](workflow.md) for routing, handoffs and what to do when a check is missing.

## Shared playbook and project instructions

This repo holds the reusable workflow. Each app’s `AGENTS.md` supplies its own teams, commands, environments and release rules. The [reference stack](config/project-stack.md) uses Linear, GitHub, Vercel, Supabase and Playwright. If an app uses other tools, use the [equivalents guide](config/stack-equivalents.md) to map them to the same steps.

The role prompts and skills are Markdown. Use the [harness setup](config/README.md) for Codex or Claude Code skill discovery, or point another harness directly at the files. A fresh session can take over using the recorded issue and handoff.

## Projects

Smaller experiments can live here. Tools with their own documentation and tests can live in their own repos and be linked here.

| Project | What it does |
| --- | --- |
| [UX Design Companion](https://github.com/willbergin/ux-design-companion-agent) | Helps explore UX ideas, build HTML prototypes and review interfaces. Use it with the [design handoff](prompts/design-handoff.md) when a flow needs shaping. |

See [maintaining the playbook](config/maintaining.md) when adding or changing a shared instruction.
