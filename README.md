# AI setup

This is where I keep the AI resources I use across my projects: agents, skills, reusable prompts and configuration notes.

Smaller experiments can live here. When something grows into a more complete tool with its own documentation and tests, I'll give it a separate repository and link to it from here.

## Projects

| Project | What it does | Status |
| --- | --- | --- |
| UX Design Companion | Helps explore UX ideas, build HTML prototypes and review interfaces using established UX principles. | [ux-design-companion-agent](https://github.com/willbergin/ux-design-companion-agent) |

## How I'll organise this repository

As I add resources, I'll group them by purpose:

- `agents/` for smaller standalone agent instructions
- `skills/` for reusable skill packages
- `prompts/` for prompts and templates worth keeping
- `config/` for shared setup files

Not every tool needs its own repository. The aim is to keep the things I reuse easy to find without turning this repo into a collection of unrelated projects.

## Issue delivery playbook

Use the Lead, Builder, and Reviewer roles to take a Linear issue through a GitHub pull request to a verified Vercel preview, with Supabase migration checks when needed.

- [Set up the playbook in an app repository](config/setup.md)
- [Read the issue delivery workflow](workflow.md)
- [Find skills for issue capture, peer review, documentation, learning, and recovery](workflow.md#skills-to-use-as-needed)
