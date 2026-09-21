# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Repository is alive | In the repo-facts block, inspect the archived flag, the date of the last push, the latest release date, and the five recent default-branch commits. | Pass if the repository is not archived and has either a push or default-branch commit within the last 180 days, or a release within the last 365 days. Otherwise fail. | required |
| Issue is bounded and actionable | Read the issue title, body, labels, and comments. Use the issue body to identify the requested change, reproduction/acceptance criteria, and whether it is an umbrella, tracking, or unresolved product/design request. | Pass if the issue describes one concrete bug, documentation task, or narrowly scoped feature with enough behavior or acceptance detail to identify a first PR. Fail if it is primarily a megaissue/tracking list, a codebase-wide umbrella, or a feature request whose key behavior/specification/product decision is still undefined. A specific bug may list more than one possible implementation or cause and still pass when the affected behavior is clear. | required |
| No active competing work | In the repo-facts block, inspect `assignees` and `linked_prs`; then inspect the complete comment thread for a current claim, in-progress work, or a PR link. | Pass only when there is no assignee, no open linked PR, and no comment showing someone is currently working on the issue. Treat a claim or PR as stale only when the thread explicitly shows it was abandoned/closed or the claimant was unassigned and there is no newer active work. | required |
| Contribution policy permits the work | In the repo-facts block, read the repository's stated contribution policy, especially any Generative AI or tooling section. | Pass if the policy permits contributions made with AI assistance subject to review/testing, or if no restrictive policy is stated. Fail if the policy explicitly bans AI-generated code or documentation, or otherwise makes this assignment's contribution method impermissible. | required |
| Maintainer support | Use the issue comments and the maintainer first-response sample in the repo-facts block. | Pass if a maintainer/member/collaborator gives useful issue-specific guidance, or if at least one of the five sampled recently updated issues received an owner/member/collaborator response within 30 days. Otherwise mark unclear. | preferred |
| Newcomer signal | Inspect the issue labels and body for `good first issue`, `help wanted`, a first-timer walkthrough, or an explicit invitation to small contributions. | Pass if at least one of those signals is present; otherwise mark unclear. This check ranks accepted issues only. | preferred |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->

Accept exactly when every required check passes. Preferred checks never
change the verdict; use them only to rank accepted issues. For required
checks, treat `unclear` as a failure. For preferred checks, report
`unclear` as `unclear` and do not reject the issue for it.
