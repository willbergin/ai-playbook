# Project stack

## Default for a new TypeScript web app

Use Next.js and TypeScript on Vercel when they fit the project. Use Supabase Postgres for application data, plus Supabase Auth and Storage where the app needs them. Use Linear for work tracking and GitHub for changes, checks, and review. Capture the actual choices and commands in the app’s [project context](../prompts/project-context.md).

## PR checks and browser evidence

Configure GitHub Actions to run the app’s build, lint, type checks, and test commands as applicable. Start with one Playwright test for the main user journey. Run it against a locally started test app in CI or a matching Vercel preview backed by nonproduction Supabase. Seed predictable fixtures and use test accounts. If a matching preview is required, wait for the candidate deployment before testing. Retain the test report or failure trace in GitHub and record the check and candidate SHA in the handoff. Use [verify-preview](../skills/verify-preview/SKILL.md) for preview evidence. [Playwright CI](https://playwright.dev/docs/ci)

## Production errors and usage

- **Sentry** when users arrive. Tag errors with environment and release. Capture the event link, release, and affected journey when invoking [diagnose-failure](../skills/diagnose-failure/SKILL.md). Configure scrubbing for sensitive fields. [Sentry for Next.js](https://docs.sentry.io/platforms/javascript/guides/nextjs/)
- **Vercel Web Analytics** for traffic and page views. **PostHog** when you need event-based questions such as onboarding drop-off or feature adoption. Define the question and event names first. Keep personal data out of event properties unless the app explicitly requires and permits it. [Vercel Web Analytics](https://vercel.com/docs/analytics) · [PostHog product analytics](https://posthog.com/docs/product-analytics)

Use the [instrumentation brief](../prompts/instrument-feature.md) when a feature needs analytics or error reporting.

## Apps that call AI models

Use the AI SDK for TypeScript where it fits. Keep provider and model selection in server-side configuration and keep prompts and output contracts versioned. Store provider credentials in the runtime secret store. [AI SDK providers and models](https://ai-sdk.dev/docs/foundations/providers-and-models)

Version a small evaluation dataset in the app repo. Include representative requests, edge cases, expected behaviours, and a scoring rubric. When changing a model or prompt, use [evaluate-ai-change](../skills/evaluate-ai-change/SKILL.md) to compare baseline and candidate. Record model IDs, prompt revision, settings, quality results, latency, and estimated cost. Use deterministic assertions for required output structure and review subjective examples against the rubric. Document the acceptance thresholds in the app’s project instructions and keep paid evaluation runs explicit or on a configured CI job.
