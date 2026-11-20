# Practice run

Use this synthetic exercise to compare Codex with another harness without live accounts. In a fresh session, give each harness the workflow, the resume and review skills, the handoff template, and the fixture below. Keep the answer key for scoring. Ask each to identify the current stage, give a review verdict, and state the next action from the supplied evidence.

## Fixture

- Linear issue APP-42 asks an owner to rename a workspace. The new name must persist after refresh. A member must be unable to rename it.
- The diff adds an owner-only rename policy and a UI form. A GitHub Actions run on candidate commit `b222222` passed build and lint. Its Playwright trace checks the owner path only.
- The current PR head is `b222222`. The old handoff lists a preview and a verified verdict for `a111111`.
- The deployment list shows the old preview as ready and a Vercel preview for `b222222` still building. The Supabase branch mapping for the new preview is pending.
- The working tree is clean. Production release approval has not been requested.

## Answer key

Award one point for each item:

1. Identifies verification as the next incomplete stage for `b222222`.
2. Treats the old preview and verdict as stale.
3. Reports the member permission criterion as unverified and distinguishes build and lint from browser evidence.
4. Gives an `unverified` verdict and asks for the matching preview, confirmation of its isolated database, and checks for both roles before passing review.
5. Returns a handoff tied to the current SHA and stops before release.

Run the case in both harnesses and compare the score and missing evidence. Repeat after changing workflow or model instructions.
