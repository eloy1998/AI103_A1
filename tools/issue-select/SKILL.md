---
name: issue-select
description: Grade a candidate open-source issue against a written rubric and decide whether it is worth taking as a first contribution. Use when evaluating a GitHub issue URL or an eval snapshot file as a potential first issue.
---

# issue-select: rubric-driven first-issue grading

You are grading one candidate issue to answer a single question: should a newcomer take this as their first contribution to this repo? Execute every check in `rubric.md` against evidence; do not decide from gut feel.

## Inputs

Accept either GitHub issue URLs (live mode) or an eval snapshot bundle (eval mode). In live mode, read `scope.md` first and refuse candidates outside its repository. In eval mode, use only the bundle text and ignore `scope.md`; do not fetch anything.

## Workflow

1. Read the rubric and list its checks and verdict rule.
2. Gather the exact evidence named by each check.
3. Grade every check `pass`, `fail`, or `unclear`, with a one-line evidence fact or quote.
4. Apply the verdict rule. The only verdicts are `accept` and `reject`.
5. With multiple live URLs, grade independently, then rank accepted issues using the fit profile in `scope.md`.

## Output format

Before the final block you may provide a short summary. End with exactly one fenced JSON block, and put nothing after it:

```json
{
  "item": "<issue URL or bundle id>",
  "checks": [
    {"name": "<check name>", "grade": "pass|fail|unclear", "evidence": "<one line>"}
  ],
  "verdict": "accept|reject"
}
```

For multiple live issues, the final block is an array of these objects, with accepted issues first in fit order.

## Grading discipline

Evidence comes first: name the fact that decided every grade. The rubric controls the verdict. Treat `unclear` as the rubric directs; when it does not specify, treat it as fail. In eval mode, the bundle is the whole world and the capture date controls recency thresholds. Do not treat a good-first-issue label as proof that work is unclaimed; inspect assignees, linked PRs, and comments.
