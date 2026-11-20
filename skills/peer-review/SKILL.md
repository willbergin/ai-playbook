---
name: peer-review
description: Request a read-only second opinion from another model on a specific candidate commit and verify the findings.
---

1. Prepare the [peer-review prompt](../../prompts/peer-review.md) with the issue, acceptance criteria, base and candidate SHAs, and the diff or PR link. Share only material approved for the target provider. Remove secrets and private data from supplied excerpts.
2. Run the prompt in a fresh session using a different model where available. If you cannot invoke it, return the filled prompt for the user to run and record the review as pending.
3. Give the findings to the Lead. Verify each against the candidate code or safe project checks. Record the evidence and a disposition of fix, dismiss, or defer, with rationale. Route confirmed fixes to Builder and flag unresolved blockers.
4. Record the reviewed SHA and coverage gaps. Recheck affected findings when the candidate changes. Use review-issue for acceptance and preview verification.
