---
name: release
description: Prepare an explicitly requested production release or confirm a production deployment and close its Linear issue.
---

## Inputs

Issue, current PR commit, review verdict for that commit, required CI results, project release process, and migration plan if needed.

## Procedure

1. Confirm the reviewed SHA is the current GitHub PR head and required GitHub checks have passed. Follow the repository's branch protection or rulesets. Summarize the release target, any migration sequencing, smoke checks, and recovery plan.
2. Treat a merge to the production branch as a production action when Vercel auto-deploys it. Follow the project's approval mechanism. Wait for explicit production authorization and required approvals before releasing.
3. Use the project's approved CI or release path. For database changes, verify the intended target and migration status before relying on the new schema. Follow the project recovery plan if migration or deployment fails.
4. Verify the intended change reached production and run the configured smoke checks. Record the production deployment and outcome. Update Linear to Done after successful verification when authorized.

## Output and stop

Return `ready for approval`, `released and verified`, or `blocked`, with links and the evidence that supports the status.
