# Task 3 — Sivakarthick: Code review, approve, merge PR

Pranesh has opened a PR (`pranesh/chapter-2` → `main`). Your job is to review it like a
real teammate would, then merge it.

## Objective

Learn: reviewing a diff on GitHub, leaving PR comments, approving a PR, merging a PR
(and the difference between merge strategies), deleting a merged branch.

## Steps

1. Go to the PR on GitHub.com. Open the **Files changed** tab.
2. Leave at least **one comment** on a specific line (even something small — e.g. a
   suggestion or a question). This is to practice inline PR review comments.
3. Locally, check out the PR branch to test it yourself (optional but recommended):
   ```
   git fetch origin
   git checkout pranesh/chapter-2
   git pull origin pranesh/chapter-2
   cat story.md
   ```
4. Back on GitHub, click **Review changes** → choose **Approve** → submit.
5. Merge the PR. Use the **"Create a merge commit"** option (not squash, not rebase —
   we want a visible merge commit for this one; other tasks will use different strategies).
6. After merging, delete the `pranesh/chapter-2` branch (GitHub will prompt you, or use
   the button on the merged PR page).
7. Locally, sync up:
   ```
   git checkout main
   git pull origin main
   git log --oneline --graph
   ```
   Notice the merge commit in the graph.

## Handoff

Tell **Raghul** that `main` now has Chapter 2 merged, and that they should branch from
the latest `main`.

## If something goes wrong

- Merge button greyed out? Check if the PR shows conflicts — it shouldn't yet at this stage.
- Accidentally approved your own review by mistake / want to re-review? You can dismiss
  and re-submit a review on GitHub.

## What I did (fill this in before handing off)

List every command/action you took (including GitHub UI actions like "clicked Approve",
"merged with merge commit") in order, with a one-line note on why.
