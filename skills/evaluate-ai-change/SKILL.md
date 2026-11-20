---
name: evaluate-ai-change
description: Compare a candidate AI model, provider, or prompt with the current baseline using the app’s versioned evaluation cases.
---

## Inputs

Candidate SHA, baseline and candidate configurations, versioned dataset and rubric, evaluation command, and project thresholds.

## Procedure

1. Record dataset and rubric revisions, baseline and candidate model IDs, prompt revisions, parameters, and thresholds before running. Use the app’s approved fixtures and provider configuration.
2. Run both on the same cases and comparable settings. Keep model calls within the configured evaluation budget. If live calls are unavailable, report which deterministic checks can run and which comparisons are pending.
3. Check required output contracts with deterministic assertions and score qualitative outputs with the same rubric. Report per-case regressions, latency, and cost or token usage. State the sample size and label cost estimates. Keep failed or skipped cases visible.
4. Compare results with the project thresholds. Flag any missing baseline, rubric, pricing data, or thresholds that prevent a decision. Give the Reviewer the report and link it to the candidate SHA.

## Output

Return baseline and candidate results, case-level regressions, threshold outcomes, and a verdict of pass, fail, or incomplete. Repeat affected evaluations if the candidate configuration changes.
