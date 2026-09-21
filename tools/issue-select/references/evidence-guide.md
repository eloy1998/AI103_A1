# Evidence guide: where first-issue signals live

## Maintainer and repository activity

In live mode inspect the repository front page, recent default-branch commits, releases, archive banner, and a sample of recently updated issues. In eval mode use the repo-facts block's `archived`, `last push`, `latest release`, five recent commits, and maintainer response sample.

## Scope

Read the issue body, labels, and complete comment thread. A bounded issue names one concrete behavior or change and has enough reproduction or acceptance detail for a first PR. An umbrella/tracking list, unresolved product decision, or long design debate is not bounded. A short bug report can still be bounded.

## Competing work

Inspect assignees, linked PRs, and comments for claims or active work. An open linked PR or current in-progress comment blocks the issue. A closed or explicitly abandoned attempt does not, unless newer work is active.

## Contribution policy

Read `CONTRIBUTING.md`, linked contributor docs, AI policy files, and templates. An explicit ban on AI-generated code or documentation fails; disclosure, review, testing, and understanding requirements are conditions rather than bans; silence passes. In eval mode use the contribution-policy line in repo facts.

All live evidence must come from the candidate repository. All eval evidence must come only from the snapshot bundle, measured against its capture date.
