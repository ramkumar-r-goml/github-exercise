# Task 7 — Diwakar: Tags, CHANGELOG, and exploring history

By now Vasantharaj's Chapter 4 PR should be merged (confirm with them — merge it
yourself on GitHub if they've asked you to). Your job is to mark this point in history
as a "release" and get comfortable digging through Git history.

## Objective

Learn: `git log` (with options), `git diff`, `git blame`, `git tag`, annotated tags,
pushing tags, writing a CHANGELOG from history.

## Steps

1. Sync:
   ```
   git checkout main
   git pull origin main
   ```
2. Explore history (just run these and read the output — no need to save it anywhere):
   ```
   git log --oneline --graph --all
   git log -p story.md          # full diffs per commit, press q to quit
   git diff HEAD~3 HEAD -- story.md
   git blame story.md
   ```
   `git blame` shows which commit last touched each line — useful for "who wrote this
   and why" archaeology.
3. Create a `CHANGELOG.md` at the repo root summarizing what happened, chapter by
   chapter, using what you saw in `git log`. Example structure:
   ```
   # Changelog

   ## v1.0.0 - <today's date>
   - Chapter 1 added (Cathrin)
   - Chapter 2 added via PR + review (Pranesh, Sivakarthick)
   - Chapter 3 added, merge conflict resolved (Raghul, Srinivasan)
   - Chapter 4 added via rebase-cleaned PR (Vasantharaj)
   ```
4. Branch, commit, push, PR — same pattern as before (by now this should feel familiar):
   ```
   git checkout -b diwakar/changelog
   git add CHANGELOG.md
   git commit -m "Add CHANGELOG"
   git push -u origin diwakar/changelog
   ```
   Open the PR, merge it yourself this time (merge commit), delete the branch, then
   `git checkout main && git pull origin main`.
5. Now tag this point as a release using an **annotated tag** (annotated, not
   lightweight, because it stores author/date/message like a commit):
   ```
   git tag -a v1.0.0 -m "First four chapters complete"
   git push origin v1.0.0
   ```
6. Confirm on GitHub.com under the repo's **Tags** (or **Releases**) section that
   `v1.0.0` appears.

## Handoff

Tell **Mrithip** that `v1.0.0` is tagged and `main` has the CHANGELOG — they're doing
the final review and closing out the exercise.

## If something goes wrong

- Tag pushed to the wrong commit? Delete it and redo:
  ```
  git tag -d v1.0.0
  git push origin :refs/tags/v1.0.0
  ```
  then re-tag correctly.
- `git log -p` output looks overwhelming — that's normal, press `q` to exit the pager
  at any time.

## What I did (fill this in before handing off)

List every command you ran, in order. Explain in your own words: what's the difference
between a commit and a tag? What does `git blame` tell you that `git log` doesn't?
