---
name: verify-preview
description: Verify a preview for a candidate revision and record browser test evidence for the issue review.
---

## Inputs

Change request and candidate revision, acceptance criteria, deployment service, approved nonproduction targets, and the app’s browser test instructions.

## Procedure

1. Confirm the change request head and look up a ready deployment for that revision using the stack profile. If the project has no preview capability, record it as unavailable and list any alternative evidence. Record the deployment URL and ID. A branch alias can move, so use the deployment-specific URL when available.
2. Before running journeys that read or write app data, confirm the preview’s data target from the deployment or project mapping. Use the approved nonproduction environment and test accounts or fixtures. If the revision or required environment is uncertain, report the blocker before running those journeys.
3. Reuse CI results only when they cover the same revision, preview, and relevant journeys. Otherwise run the configured browser test command against that deployment. A local CI run can support code checks. Record preview coverage separately. If the browser runner is unavailable, report manual evidence and any missing required checks.
4. Record the result for each journey and link the CI check, report, or failure trace where available. Include skipped cases and why they were skipped. Recheck the change request head before returning.

## Output

Return the candidate revision, deployment and database target, journey results, evidence links, and outstanding checks. Pass this evidence to review-issue for the acceptance verdict.
