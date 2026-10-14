# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/zxcalc/zxlive/issues/555

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
I've finished gathering evidence from the GitHub API, because gh isn't installed here. Here is the live grade. Capture date is 2026-10-13, and references/evidence-guide.md doesn't exist, so I took each signal from the rubric's own evidence column.

Your scope.md now names this issue, so I graded it. The staff text above that line still says only Path Review issues are candidates, so you may want to change that line back before submitting.

Verdict: accept. All 8 required checks pass.

- ai-allowed: CONTRIBUTING.md has no AI statement, and AGENTS.md, CLAUDE.md and AI_POLICY.md all return 404.
- issue-unclaimed: There are no assignees and no linked PRs. The only comment is the maintainer's contributor notes, not a claim.
- issue-unplanned: Roadmap issue #614 lists it as an unchecked item, "Add missing previews for basic rewrite rules (issue 555)". That is an open-work list for contributors, not a statement that anyone is working on it. The 2026-10-09 maintainer comment invites someone to pick it up. This is the closest call.
- maintainer-alive: All 5 recent commits are by RazinShaikh, and RazinShaikh is a COLLABORATOR.
- scope-suitable: It carries the good first issue label ("Good for newcomers").
- scope-pulled: Of the 5 most recent PRs, only #602 is closed-unmerged, and it isn't linked to this issue. That makes 0 linked closed-unmerged PRs.
- scope-focused: It covers three basic-rule previews (id_simp, fuse_simp, remove_self_loops) in one area, which counts as a single task.
- repo-alive: The repo isn't archived, and the newest commit is 2026-10-09, 4 days before capture.

Preferred checks
- maintainer-responsive: Pass. In my sample of 5 recently updated issues, 3 got a first maintainer comment within 120 days (53.4, 1.0 and 65.7 days). The other two were 585.7 days and no maintainer comment. This is my own sample, not a harness one.
- scope-language: Pass. The repo is Python, Jupyter Notebook and Shell, which is 3 languages.
- comments-punctual: Fail. Only 1 of 5 got a first maintainer comment within 30 days (1.0 day).

Fit: Python is your main language, so it matches your profile. The maintainer's comment names the files to start from (zxlive/rewrite_data.py, zxlive/tooltips/, zxlive/rewrite_action.py) and asks for tooltip screenshots in the PR.

{
  "item": "https://github.com/zxcalc/zxlive/issues/555",
  "checks": [
    {"name": "ai-allowed", "grade": "pass", "evidence": "CONTRIBUTING.md has no AI statement; AGENTS.md, CLAUDE.md and AI_POLICY.md all return 404"},
    {"name": "issue-unclaimed", "grade": "pass", "evidence": "assignees: []; no linked PRs; the only comment is maintainer contributor notes, not a claim"},
    {"name": "issue-unplanned", "grade": "pass", "evidence": "Roadmap #614 lists it as an unchecked open item; no statement it is being worked on; maintainer comment invites pickup"},
    {"name": "maintainer-alive", "grade": "pass", "evidence": "Last 5 commits (2026-10-08 to 2026-10-09) by RazinShaikh; RazinShaikh (COLLABORATOR) commented"},
    {"name": "scope-suitable", "grade": "pass", "evidence": "Labels include 'good first issue' (Good for newcomers)"},
    {"name": "scope-pulled", "grade": "pass", "evidence": "Of the 5 latest PRs only #602 is closed-unmerged and it is not linked to this issue, so 0 linked closed-unmerged"},
    {"name": "scope-focused", "grade": "pass", "evidence": "Three same-kind rule previews (id_simp, fuse_simp, remove_self_loops) in one area"},
    {"name": "repo-alive", "grade": "pass", "evidence": "archived: false; newest commit 2026-10-09 vs capture 2026-10-13"},
    {"name": "maintainer-responsive", "grade": "pass", "evidence": "3 of 5 sampled issues got a first maintainer comment within 120 days (53.4, 1.0, 65.7 days)"},
    {"name": "scope-language", "grade": "pass", "evidence": "Python, Jupyter Notebook, Shell: 3 languages, Python is common"},
    {"name": "comments-punctual", "grade": "fail", "evidence": "Only 1 of 5 sampled first maintainer comments within 30 days (1.0 day)"}
  ],
  "verdict": "accept"
}
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrasing does not satisfy them.

**Run history**

I wasn't necessarily keeping track of the scores for each full run-eval.py run, but I remember long stretches of getting 12-16 / 20 passes, with all of the discrepancies being with the scope and policy categories. "scope" would consistently score 0/4 due to a problematic check, and "policy" remained 0/1 because I didn't have a check for AI use policy yet.

By the end of many, many hours of revising the skills, though, I finally got a passing run of 19/20, now recorded in eval-run.txt. Here are the specific categories:

```
categories: claimed 4/4  clear-accept 8/8  dead-repo 3/3  policy 1/1  scope 3/4
agreement: 19/20 scored items  (bar: 18/20: PASS)
```

**Issue analysis**

Here's the verdict from the terminal:

```
grading 1 bundle(s) with rubric.md, model sonnet, 5 worker(s)...
  issue-04: accept

item      gold    verdict  agree  note
issue-04  accept  accept   yes    

agreement: 1/1 scored items
```

Here's the reasoning from Claude Code's eval run of just the chosen issue:

```
issue-04 (zxcalc/zxlive#555, "Missing several basic rule previews"): accept. All 7 required checks pass.

- ai-allowed: pass. CONTRIBUTING.md has "no statement on AI or contribution tooling".
- issue-unclaimed: pass. "assignees: none; linked PRs: none", and there are no comments.
- issue-unplanned: pass. Nothing in the issue says a maintainer is working on it.
- maintainer-alive: pass. The last 5 commits are by RazinShaikh and 96-LB, neither a bot.
- scope-suitable: pass. It carries the "good first issue" label.
- scope-pulled: pass. The bundle lists no linked PRs, so there are zero closed-unmerged linked PRs.
- scope-focused: pass. It's a batch of same-kind previews in one area (Proof mode).
- repo-alive: pass. The repo is not archived an8-04, one day before capture.

Preferred checks (these only affect ranking):
- maintainer-responsive: pass. 3 of the 5 sampled issues got a maintainer comment (#462, #507, #513), all within 120 days.
- scope-language: pass. No languages are listed
- comments-punctual: fail. Only 2 of the 5 got a comment within 30 days (#462 at 25.8 days, #507 at 0.4).

I graded the bundle by hand from issue-04.md. I did not run the harness or write a run file (--save-run).

{
  "item": "zxcalc/zxlive#555 (issue-04)",
  "checks": [
    {"name": "ai-allowed", "grade": "pass", "ev statement on AI or contribution tooling"},
    {"name": "issue-unclaimed", "grade": "pass", "evidence": "assignees: none; linked PRs: none; 0 comments"},
    {"name": "issue-unplanned", "grade": "pass"hat the issue is being worked on or on atimeline"},
    {"name": "maintainer-alive", "grade": "passs by RazinShaikh and 96-LB, no [bot] authors"},
    {"name": "scope-suitable", "grade": "pass", "evidence": "Labels include 'good first issue'"},
    {"name": "scope-pulled", "grade": "pass", " 0 closed-unmerged linked PRs"},
    {"name": "scope-focused", "grade": "pass", "evidence": "Several same-kind rule previews in one area (Proof mode)"},
    {"name": "repo-alive", "grade": "pass", "evt commit 2026-08-04 vs captured 2026-08-05"},
    {"name": "maintainer-responsive", "grade": "pass", "evidence": "3 of 5 sampled issues got a maintainer comment within 120
days (25.8, 0.4, 92.1 days)"},
    {"name": "scope-language", "grade": "pass", "evidence": "No languages mentioned; allowed to pass"},
    {"name": "comments-punctual", "grade": "faifirst maintainer comments within 30 days (25.8,0.4); #513 took 92.1"}
  ],
  "verdict": "accept"
}
```

**Check rationale**

[One check from the `rubric.md` uploaded to `tools/issue-select/`, quoted as it is
currently written, with the reasoning behind its current form.]

```
| scope-suitable | Issue section: title, body; Comments section | Pass if the issue is labeled with a tag or other mention of being "good first issue", "easy", or similar labels about being suitable for a first PR to take on. If unclear, pass only if the issue body describes an observed/desired behavior of the program, and no maintainer says a key input or decision for a plan of action is still open (e.g., "TBD", "maybe"). | required |
```

This. Check. Was a reeeal pain. It was originally part of a check called "scope-actionable" that broadly checked if the issue body or comments had some plan of action or suggestions for what to look at or do to address the issue. However, that check was split into "scope-focused" and this when I found out it was way too broad with its own scope, taking on two separate problems in one go.

Even after the split, though, this check would constantly fail due to being vague in what it was looking for. The original wording was something along the lines of "...If unclear, pass only if the issue body has an explicitly stated plan of action for fixing/addressing a given feature", which would never fire due to a lack of direction for where to look and what constituted a "plan of action". In the end, I had to be more objective and change that to "...If unclear, pass only if the issue body describes an observed/desired behavior of the program..." to give more specificity. Claude Code also suggested the addition of "...and no maintainer says a key input or decision for a plan of action is still open (e.g., "TBD", "maybe")" to catch some false positives created by just having an observation in the issue body.

**Trade-offs**

[What the quoted check gives up. Any one of these is a complete answer: an issue whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

This check will give up on issues that don't have a very actionable description, and is liable to give up on issues without a "good first issue" tag or so. However, this is fine, since I'm not planning on accepting any issues that don't have plans of action, nor any concepts of a plan of action. 

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

[Answer all three:

1. The issue's fit to your interests and to the time available.
2. What the verdict identified correctly, and what you weighed that the rubric could
   not.
3. The anticipated difficulty in claiming it.
]

I've always been interested in learning quantum computing since it seems enormously powerful, but I never got around to doing a deep dive into studying it. This issue seems like it can help me start that journey while doubling as the main project I can work on here, which is a win-win to me. Granted, learning the basics of quantum computing is potentially going to be a rather big hurdle to working on this issue. At a glance, this issue just involves implementation of tooltips and previews on button hovers. But, if more is required in regards to knowledge of the rules themselves, then this could be tough to fit into the last 5 weeks of this course.

The rubric seemed to catch everything about this issue correctly, probably because the issue description itself is only one line long. It saw that the issue was focused on just one area (implementing rule previews), was suitable for a first issue due to the "good first issue" tag, and was both unclaimed and recent. Outside of that, it correctly gauged the active state of the repo from the maintainer comments and commits, as well as the AI use policy due to the lack of mentions of AI use in the contribution guide. 

Claiming this issue shouldn't be too difficult since as of writing this (10/13/2026), there is now a bump comment from the maintainer detailing a plan of action for anyone who takes it. I get the impression that they're egging on people to take this issue, and are eager for someone like me to give it a shot.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
