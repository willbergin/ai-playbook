---
name: shape-issue
description: Turn a project idea or Linear issue into a scoped milestone or an implementation-ready issue.
---

## Inputs

User goal or existing issue ID, project context, and any known constraints.

## Procedure

1. Read the existing issue and search the target Linear project for overlapping work when access is available.
2. Describe the user outcome, scope, dependencies, and observable acceptance criteria. For a project, draft the first milestone and order its issues by dependency. Use the issue template.
3. Preserve a clear existing plan. Resolve material ambiguities with the user. State reversible assumptions and continue when practical.
4. Reuse matching issues. Create or update issues only when authorized. After ambiguous write failures, re-read Linear before retrying. Use drafts when writes are unavailable.

## Output and stop

Return issue IDs or drafts, dependencies, acceptance criteria, and any unresolved decision. Hand off the first ready issue.
