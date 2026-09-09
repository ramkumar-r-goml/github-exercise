# Task 4 — Raghul: Set up a merge conflict (on purpose)

`main` now has Chapters 1 and 2. In real teams, two people often edit the same lines at
the same time without realizing it. You're going to recreate that on purpose so that
Srinivasan (Task 5) gets real practice resolving a merge conflict.

## Objective

Learn: how conflicting edits happen, `branch`, editing the **same lines** another
branch will also touch.

## Steps

1. Sync and branch from latest `main`:
   ```
   git checkout main
   git pull origin main
   git checkout -b raghul/chapter-3
   ```
2. Add a new section at the **end** of `story.md`:
   ```
   ## Chapter 3: The Turning Point

   <your 2-3 sentences here>
   ```
3. Commit and push:
   ```
   git add story.md
   git commit -m "Add Chapter 3 (Raghul's version)"
   git push -u origin raghul/chapter-3
   ```
4. **Do not open a PR yet.** Instead, immediately create a *second* branch from `main`
   (not from your first branch) that edits the exact same spot:
   ```
   git checkout main
   git checkout -b raghul/chapter-3-alt
   ```
   In `story.md`, add a **different** "## Chapter 3: ..." section (different heading
   text, different sentences) at the same location (end of file).
5. Commit and push this second branch too:
   ```
   git add story.md
   git commit -m "Add Chapter 3 (alternate version)"
   git push -u origin raghul/chapter-3-alt
   ```
6. Open a PR for `raghul/chapter-3` → `main` and **merge it yourself** (use "Create a
   merge commit" again, delete the branch after). Now `main` has your first Chapter 3.
7. Open a **second PR** for `raghul/chapter-3-alt` → `main`. GitHub will now show this
   PR has a **merge conflict** with `main` (because `main` already has a different
   Chapter 3 in the same spot). Leave this PR **open, unresolved** — do not merge it,
   do not fix it. That's the point.

## Handoff

Tell **Srinivasan**: "PR `raghul/chapter-3-alt` has a merge conflict against `main` —
go resolve it." Give them the PR link/number.

## If something goes wrong

- If GitHub says no conflict (rare — depends on exact lines edited), make sure both
  Chapter 3 versions edited the *same line range* at the end of the file, not clearly
  separated sections.

## What I did (fill this in before handing off)

List every command you ran, in order, with a one-line note on what it did and why —
including why this setup produces a conflict.
