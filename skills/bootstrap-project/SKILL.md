---
name: bootstrap-project
description: Prepare an application repository for the issue delivery playbook and report which checks and service connections are ready.
---

## Inputs

Application repo, existing project instructions, and any known service targets. Use the [project context template](../../prompts/project-context.md) and [stack guide](../../config/project-stack.md).

## Procedure

1. Inspect the repository instructions, manifests, lockfiles, workflows, and migration directories. Record the actual build, test, lint, and smoke-check commands. Preserve existing conventions. For a new web app, propose the stack guide’s baseline where it fits.
2. Identify the GitHub repository and required checks, Linear project and states, Vercel preview and production targets, and Supabase environment mapping. Use read-only checks where tools are available. Mark each connection as verified, configured but unverified, missing, or not applicable. Record the evidence and omit secret values.
3. Merge confirmed project context into the app’s AGENTS.md, preserving existing instructions. Flag unresolved values and list who or what can supply them. Follow the harness setup for skill discovery if requested.
4. Identify the first critical browser journey and how to run it in CI against nonproduction data. Apply optional stack guidance only where the app needs it.

## Output and stop

Report what is ready, the evidence for each connection, remaining setup, and a first-run prompt for a real issue. Keep service provisioning and production changes for a separately requested task.
