# AI playbook

Reusable roles and skills for taking an issue through review and release with your project’s tools.

## Install in an application repository

Copy the contents of this repository to `ai-playbook/` at the application repo root. Fill out `prompts/project-context.md` and merge it into the app's `AGENTS.md`. Keep existing project instructions. Record the actual check commands, issue tracker states, production branch, and environment mapping before using the matching integrations.

You can also run [bootstrap-project](../skills/bootstrap-project/SKILL.md) to inspect an existing repo and fill in verified context. See the [stack guide](project-stack.md) for browser checks, error monitoring, product analytics, and AI features.

You can start with plain file access. For native skill discovery, follow [the harness setup](README.md).

## Start a run

From the application repository, give your agent this instruction:

> Read AGENTS.md and ai-playbook/workflow.md. Take APP-42 to a verified preview. Use the playbook roles and record the handoff. Stop at preview verification.

For a new project, start with:

> Read ai-playbook/workflow.md and use the Lead role to shape this idea into a first milestone and independently shippable issues. Keep the backlog as a draft until I authorize publishing it to the issue tracker.

Start review in a fresh session if your harness cannot delegate independently. Give it the issue, PR, commit SHA, and preview. The same files work with another provider. A chat-only model can use pasted files and return drafts or review notes based on supplied evidence.

For a one-off task, name the skill or ask the harness to read its `SKILL.md` directly. For example, “Use create-issue to capture this bug, then resume the current task.” See the [skill index](../workflow.md#skills-to-use-as-needed) for when to invoke each one.

To compare harnesses before connecting live services, use the [practice run](../examples/practice-run.md).

## Connect services

Choose the [reference stack](project-stack.md) or use the [equivalents guide](stack-equivalents.md) to map your own tools. Record the profile and actual commands in the app’s `AGENTS.md`. Keep credentials in the runtime or CI secret store.
