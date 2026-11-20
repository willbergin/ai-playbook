---
name: resume-issue
description: Reconstruct work on a tracked issue from the repo and existing records, including work in progress before a PR exists.
---

1. Read the project instructions, tracked issue, and any checkpoint or handoff. Inspect the current branch, HEAD, and working tree. Look up a matching change request and preview when available.
2. Compare recorded state to current evidence. Preserve local edits. Flag conflicts, stale review results, and uncommitted work that a different checkout cannot see.
3. Identify the latest completed stage, pending checks, blockers, and next authorised action. Reuse existing issue and PR records.
4. Return a concise [checkpoint](../../prompts/checkpoint.md) and continue if requested. If a dependency is missing, name it and continue any independent checks.
