---
name: diagnose-failure
description: Trace a failed GitHub check, Vercel deployment, or Supabase migration to its cause.
---

1. Identify the failing step, candidate SHA, and environment. Read the relevant check output, deployment logs, or migration history. Record the first actionable error and any gaps in access.
2. Compare with the last known successful run if available. Check configuration, dependency, and schema changes that explain the failure. Use local or preview environments for safe confirmation.
3. For a partially applied migration, inspect actual schema and recorded migration status before proposing a retry. Route production recovery through the approved release process.
4. Return the evidence, confirmed or likely cause, smallest corrective action, and verification steps. If authorised, apply the scoped fix and rerun the affected checks.
