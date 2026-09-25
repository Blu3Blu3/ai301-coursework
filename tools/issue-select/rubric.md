---
name: issue-rubric
description: The rubric to which a candidate open-source issue is graded against in terms of viability and worthiness as a first open-source contribution. Used when evaluating a GitHub issue URL or an eval snapshot file as a potential first issue.
---

# Rubric: is this a good first issue?

The following checks to use in grading a candidate open-source issue. Their format is:

- *Check*: A short name used as an attribute in the output JSON.
- *Evidence*: What to look at and where it's located; this is the source (repo-facts block, issue body, comment thread, or the locations in references/evidence-guide.md). Valid sources would be things like "the last 5 recent commits", not "the repo" or "commits about 'x' feature".
- *Pass condition*: A condition to apply to the check, probably written by someone else. Prefer thresholds with numbers ("a maintainer commented within 30 days") over adjectives ("maintainer is responsive").
- *Weight*: `required` (a fail here rejects the issue) or `preferred` (never changes the verdict, but helps in improving an issue's spot in your ranking).

## Checks

Number | Check | Evidence | Pass condition | Weight
| --- | --- | --- | --- | --- |
1 | repoAlive | most recent commit | last commit made within the last 3 months | required |
| --- | --- | --- | --- | --- |
2 | maintainerAlive | most recent commit | last commit made by maintainer (not a bot!) | required |
| --- | --- | --- | --- | --- |
3 | maintainerComments | 5 most recent comments | maintainer responded to 3+ comments | required |
| --- | --- | --- | --- | --- |
4 | scopeAbilities | issue body | issue highlights 1 main bug to fix (best rating), or 2-3 (ok rating) | required
| --- | --- | --- | --- | --- |
5 | scopeLanguage | repo-facts block or README | repo has less than 5 languages AND at least 1 is a common programming language (e.g., Python, C++, Java, etc.) | preferred |
| --- | --- | --- | --- | --- |
6 | commentsPunctual | 5 most recent comments | maintainer responded to 3+ comments within 14 days | preferred |
| --- | --- | --- | --- | --- |

## Verdict rule

To accept an issue, all required checks must pass. Preferred checks may improve an issue's ranking among multiple if they pass. If more than 1 required check is unclear, reject the issue. If a preferred check is unclear, count it as a pass.