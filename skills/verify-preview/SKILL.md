---
name: verify-preview
description: Verify a Vercel preview for a GitHub PR commit and record Playwright evidence for the issue review.
---

## Inputs

PR and candidate SHA, acceptance criteria, Vercel project, approved nonproduction targets, and the app’s browser test instructions.

## Procedure

1. Confirm the PR head and look up the ready Vercel deployment for that SHA. Record the deployment URL and ID. A branch alias can move, so use the deployment-specific URL when available.
2. Before running journeys that read or write app data, confirm the preview’s Supabase target from the deployment or project mapping. Use the approved nonproduction environment and test accounts or fixtures. If the SHA or required environment is uncertain, report the blocker before running those journeys.
3. Reuse GitHub Actions results only when they cover the same SHA, preview, and relevant journeys. Otherwise run the configured Playwright command against that deployment. A local CI run can support code checks. Record preview coverage separately. If the browser runner is unavailable, report manual evidence and any missing required checks.
4. Record the result for each journey and link the GitHub check, report, or failure trace where available. Include skipped cases and why they were skipped. Recheck the PR head before returning.

## Output

Return candidate SHA, deployment and database target, journey results, evidence links, and outstanding checks. Pass this evidence to review-issue for the acceptance verdict.
