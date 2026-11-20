---
name: review-issue
description: Independently review an issue's candidate commit and verify acceptance criteria on its matching preview.
---

## Inputs

Tracked issue, acceptance criteria, candidate commit, diff, and candidate preview.

## Procedure

1. Read the issue and diff. Use [verify-preview](../verify-preview/SKILL.md) for deployment and browser evidence when the issue requires a preview.
2. For each criterion, record how it was checked and what happened. Check relevant negative paths and existing behavior nearby. Use test accounts and fixtures for permission checks.
3. Compare the candidate commit's CI checks and local results against what the repo requires. Link required browser reports to the candidate SHA. For model or prompt changes, check the Builder’s [evaluation report](../evaluate-ai-change/SKILL.md) against project thresholds. Mark any criterion without evidence as unverified.
4. Report each finding with severity, location or user journey, expected and observed behavior, and suggested correction.

## Output and stop

Return the candidate SHA, criterion-by-criterion evidence, and one verdict. Use `verified` when required checks and preview criteria pass, `changes requested` when findings block release, or `unverified` when required evidence is missing. Review again after the candidate commit changes.
