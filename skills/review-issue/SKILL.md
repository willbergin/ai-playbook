---
name: review-issue
description: Independently review an issue's candidate commit and verify acceptance criteria on its matching preview.
---

## Inputs

Linear issue, acceptance criteria, candidate commit, diff, and candidate preview.

## Procedure

1. Read the issue and diff. Check that the preview is built from the candidate commit and uses the intended nonproduction database when applicable.
2. For each criterion, record how it was checked and what happened. Check relevant negative paths and existing behavior nearby. Use test accounts and fixtures for permission checks.
3. Compare the candidate commit's GitHub checks and local results against what the repo requires. Mark any criterion without evidence as unverified.
4. Report each finding with severity, location or user journey, expected and observed behavior, and suggested correction.

## Output and stop

Return the candidate SHA, criterion-by-criterion evidence, and one verdict. Use `verified` when required checks and preview criteria pass, `changes requested` when findings block release, or `unverified` when required evidence is missing. Review again after the candidate commit changes.
