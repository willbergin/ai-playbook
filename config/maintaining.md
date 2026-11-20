# Maintaining the playbook

When a real run turns up a gap, start with the smallest instruction that would have helped.

| Change | Where it belongs |
| --- | --- |
| A command, service, or release rule specific to one app | The app’s `AGENTS.md` |
| A tool-specific way to collect evidence | The relevant [stack profile](project-stack.md) or app mapping |
| A repeatable task shared across apps | The existing skill or a new folder under `skills/` |
| A handoff format or pasteable instruction | The relevant file in `prompts/` |
| A change in who owns a decision | The role file and [workflow](../workflow.md) |

## Add or revise a skill

Use `skills/<name>/SKILL.md` with matching `name` and a `description` that tells the harness when to use it. Give the skill its inputs, steps, evidence to return and a stopping point. Link to existing role instructions or templates where they already cover the decision. Add it to the workflow index, then try it on a real issue or a [practice fixture](../examples/practice-run.md).

## Add or revise a role

Describe what it owns, what it needs to start and what the next role receives. Show where it enters the workflow. For a specialised task that fits an existing role, start with a skill or a handoff.
