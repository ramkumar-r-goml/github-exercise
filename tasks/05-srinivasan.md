# Task 5 — Srinivasan: Resolve the merge conflict

Raghul left you an open PR (`raghul/chapter-3-alt` → `main`) that GitHub reports as
conflicting. Your job is to resolve it properly using Git locally (not the GitHub web
editor — you want the real command-line experience).

## Objective

Learn: `fetch`, `merge`, reading conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`),
resolving conflicts, `git add` on resolved files, completing a merge commit.

## Steps

1. Fetch everything and check out the conflicting branch:
   ```
   git fetch origin
   git checkout raghul/chapter-3-alt
   git pull origin raghul/chapter-3-alt
   ```
2. Merge the latest `main` into your branch — this is what will trigger the conflict
   locally so you can fix it:
   ```
   git merge origin/main
   ```
3. Git will report a conflict in `story.md`. Open the file. You'll see something like:
   ```
   <<<<<<< HEAD
   ## Chapter 3: The Turning Point (alternate version)
   ...
   =======
   ## Chapter 3: The Turning Point
   ...
   >>>>>>> origin/main
   ```
4. Resolve it by hand: decide how the two versions should coexist. Simplest approach —
   keep **both** as distinct subsections, e.g.:
   ```
   ## Chapter 3: The Turning Point

   <Raghul's original text>

   ### Alternate take

   <the alt-branch text>
   ```
   Remove all `<<<<<<<`, `=======`, `>>>>>>>` markers completely.
5. Mark it resolved and commit:
   ```
   git add story.md
   git status
   git commit -m "Resolve merge conflict in Chapter 3"
   ```
6. Push:
   ```
   git push origin raghul/chapter-3-alt
   ```
7. Go back to the PR on GitHub — it should now show as mergeable (no conflicts). Merge
   it (merge commit again), delete the branch.
8. Sync locally:
   ```
   git checkout main
   git pull origin main
   ```

## Handoff

Tell **Vasantharaj** that `main` is updated and conflict-free, and that their task
involves rebasing — they should branch fresh from this `main`.

## If something goes wrong

- `git merge origin/main` says "Already up to date"? You're on the wrong branch —
  confirm with `git branch` that you're on `raghul/chapter-3-alt`.
- Accidentally left conflict markers in the file and committed? Edit the file again,
  remove them, `git add story.md`, then `git commit --amend`.
- Want to bail out of a merge entirely and start over? `git merge --abort`.

## What I did (fill this in before handing off)

List every command you ran, in order, with a one-line note on what it did — especially
explain in your own words what the conflict markers meant.
