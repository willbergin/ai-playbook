# AI playbook

Reusable roles and skills for shipping work through Linear, GitHub, Vercel, and Supabase.

## Install in an application repository

Copy the contents of this repository to `ai-playbook/` at the application repo root. Fill out `prompts/project-context.md` and merge it into the app's `AGENTS.md`. Keep existing project instructions. Record the actual check commands, Linear states, production branch, and environment mapping before using the matching integrations.

You can start with plain file access. For native skill discovery, follow [the harness setup](README.md).

## Start a run

From the application repository, give your agent this instruction:

> Read AGENTS.md and ai-playbook/workflow.md. Take APP-42 to a verified preview. Use the playbook roles and record the handoff. Stop at preview verification.

For a new project, start with:

> Read ai-playbook/workflow.md and use the Lead role to shape this idea into a first milestone and independently shippable issues. Keep the backlog as a draft until I authorize publishing it to Linear.

Start review in a fresh session if your harness cannot delegate independently. Give it the issue, PR, commit SHA, and preview. The same files work with another provider. A chat-only model can use pasted files and return drafts or review notes based on supplied evidence.

## Connect services

- Linear uses the official MCP server where available. A Linear API client is an equivalent. Without write access, return a ready-to-paste change.
- GitHub hosts the repository, pull requests, reviews, and check results. Use Git for branches and commits, and the GitHub connector or `gh` for PRs and checks. Use GitHub Actions for repo CI where configured.
- Connect the GitHub repository to Vercel to build previews for feature branches. Read deployment status through the integration, dashboard, or CLI.
- Supabase migrations live in version control. Test locally or against a confirmed nonproduction environment. Use the repository's approved production migration process.
- Put credentials in the harness or CI secret store. Use project-scoped credentials where supported.

[Linear MCP](https://linear.app/docs/mcp) · [Vercel Git deployments](https://vercel.com/docs/git) · [Supabase deployment](https://supabase.com/docs/guides/deployment)
