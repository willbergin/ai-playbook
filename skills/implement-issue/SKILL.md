---
name: implement-issue
description: Implement an accepted issue on a feature branch, run project checks, and prepare a Vercel preview for review.
---

## Inputs

Issue and acceptance criteria, repository instructions, and target environments.

## Procedure

1. Check the working tree and reuse the issue's branch or PR if one exists. Protect unrelated changes. Use a dedicated branch or worktree when needed.
2. Make the scoped change. For database work, add a versioned migration and test it with local fixtures or a confirmed isolated Supabase branch. Verify intended role permissions with representative test users where relevant.
3. Run the repo's applicable tests, lint, type checks, and build. Capture command results. For migration changes, record the upgrade path and compatibility with the running app.
4. When authorized, push to GitHub and create a PR or update the existing one. Link the Linear issue, check the GitHub status checks for the candidate commit, and wait for the matching Vercel preview when available. Record deployment failure or missing access separately from test results.

## Output and stop

Fill out the handoff with the commit, PR, check results, preview URL and status, database target, and known gaps. Hand the candidate to review.
