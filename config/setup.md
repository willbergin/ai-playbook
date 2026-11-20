# Set up the playbook

## Add it to an app repo

1. Copy the playbook files into `ai-playbook/` at the app repo root. Copy the files from inside this repository and leave its Git metadata behind.
2. Fill in the [project context template](../prompts/project-context.md) and merge it into the app’s `AGENTS.md`. You can ask [bootstrap-project](../skills/bootstrap-project/SKILL.md) to inspect the repo and identify which details still need input.
3. Use the [reference stack](project-stack.md) or [map equivalent tools](stack-equivalents.md). Record where to look up issues, how to find checks and previews for a commit, which database previews use and what triggers production. Keep secrets in the runtime or CI secret store.
4. For automatic skill discovery, use the [harness setup](README.md). Any harness that can read files can also follow a skill by path.

## Start with one issue

Pick an issue small enough to verify in a single preview. From the app repo, paste this into your coding session and replace the example ID.

> Read AGENTS.md and ai-playbook/workflow.md. Take APP-42 to a verified preview. Record the handoff and stop at preview verification.

When review starts, give a fresh session the issue, candidate commit, change request and preview. Ask it to read `ai-playbook/agents/reviewer.md` and follow `ai-playbook/skills/review-issue/SKILL.md`. A chat-only model can review the supplied records. Record any checks that require access it doesn’t have.

For a new project, begin with the Lead.

> Read ai-playbook/workflow.md and use the Lead role to turn this idea into a first milestone and independently shippable issues. Keep the backlog in draft until I authorise publishing it.

For one-off work, name the skill or give its path. For example, “Use create-issue to capture this bug, then resume the current task.”

## Try it without live services

Run the [practice exercise](../examples/practice-run.md) in a fresh session. It includes a stale preview and one missing browser check. Compare the review verdict and next action with the answer key. Repeat in a second harness if you want to check portability.

## Update an installed copy

Copy in the updated playbook files and rerun your [skill discovery setup](README.md) to link new skills. Keep app-specific instructions in `AGENTS.md`. If you’ve edited a skill locally, compare the versions before replacing it.
