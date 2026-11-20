# Map an equivalent stack

Use the [reference stack](project-stack.md) as a worked starting point. Keep your own mapping in the app’s `AGENTS.md` using the [project context template](../prompts/project-context.md). The same roles, skills, and handoff apply.

1. Map each capability to the tools you actually use. Record the project or environment identifier, the read or write method (connector, CLI, API, or manual), and the evidence it returns.
2. Use [bootstrap-project](../skills/bootstrap-project/SKILL.md) to confirm what is reachable. Record permissions and missing capabilities. If a step requires a manual action, record its owner and what evidence they should return.
3. Check one issue end to end. Confirm the change request revision matches CI and the deployment, and confirm the test data target before running data-dependent journeys. Record each link in the handoff. A required check without evidence leaves review unverified.

| Capability | Reference stack | Example equivalent | What the workflow needs |
| --- | --- | --- | --- |
| Issue tracking | Linear | Jira | Issue ID, link, scope, acceptance criteria, and state mapping |
| Source, review, and CI | GitHub and Actions | GitLab merge requests and CI | Change request link, head commit, required check results and artifacts |
| Preview and release | Vercel | Netlify Deploy Previews | Deployment ID, exact commit, deployment URL, and approved production trigger |
| Database and migrations | Supabase | PostgreSQL with Flyway | Approved test target, fixture and migration commands, and migration results |
| Browser checks | Playwright | Cypress | Configured test command, tested URL, journey outcomes, and report |
| Monitoring and analytics | Sentry and PostHog | Datadog and Amplitude | Release or environment tag, error evidence, and event verification |
| Model evaluation | AI SDK and app eval cases | Provider SDKs and an app-owned runner | Model IDs, case and rubric revisions, thresholds, and comparable results |

## Worked example

For Jira, GitLab, Netlify, PostgreSQL, and Cypress, record the Jira project and its completion state, the GitLab repo and required jobs, the Netlify site and preview lookup method, the approved test database identifier, and the Cypress command and report path. Link the Jira issue to its merge request. Read the candidate commit from that request, locate its matching preview and CI run, confirm the preview points at the configured test database, then run Cypress against that URL. Return the same [handoff](../prompts/handoff.md) as the reference stack. Where preview hosting and source hosting are separate, document how the deployment is triggered and how the head revision is passed through and verified; the pairing requires a configured integration or CI deployment job.

For projects without previews, document which criteria can be verified with local or CI evidence. Keep required preview criteria unverified until matching deployment evidence is available.
