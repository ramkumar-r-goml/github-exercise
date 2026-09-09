# Task 6 — Vasantharaj: Interactive rebase to clean history

`main` is now conflict-free with Chapters 1–3. Your job is to add Chapter 4, but you'll
deliberately make a messy set of commits first, then clean them up with an
**interactive rebase** before opening your PR. This is a very common real-world
workflow: commit freely while working, then tidy history before review.

## Objective

Learn: `git rebase -i`, squashing commits, rewording commit messages, rebasing a
feature branch onto updated `main`.

## Steps

1. Sync and branch:
   ```
   git checkout main
   git pull origin main
   git checkout -b vasantharaj/chapter-4
   ```
2. Make **3 separate small commits** (on purpose, messy) as you write Chapter 4:
   ```
   # edit story.md: add "## Chapter 4: ..." heading only
   git add story.md
   git commit -m "wip: add heading"

   # edit story.md: add first sentence
   git add story.md
   git commit -m "wip: first sentence"

   # edit story.md: add 1-2 more sentences, fix typos etc
   git add story.md
   git commit -m "wip: finish chapter 4"
   ```
3. Check your messy history:
   ```
   git log --oneline
   ```
   You should see your 3 "wip" commits on top of main.
4. Now clean it up with an interactive rebase against `main` (squash the 3 commits into
   1 with a good message):
   ```
   git rebase -i main
   ```
   In the editor that opens, you'll see the 3 commits listed with `pick` in front of
   each. Change it to:
   ```
   pick <hash1> wip: add heading
   squash <hash2> wip: first sentence
   squash <hash3> wip: finish chapter 4
   ```
   Save and close. A second editor screen will open asking for the combined commit
   message — replace it with a single clean message, e.g. `Add Chapter 4`.
5. Confirm history is now clean:
   ```
   git log --oneline
   ```
   You should see exactly **one** new commit on top of `main`.
6. Push. Since you rewrote history on your own branch (which has never been pushed
   before), a normal push works:
   ```
   git push -u origin vasantharaj/chapter-4
   ```
7. Open a PR (`vasantharaj/chapter-4` → `main`). Leave it open for review — do not
   merge it yourself.

## Handoff

Tell **Diwakar** that your PR is open and ready for them to look at (they'll be
tagging/logging around this point, so having your PR open — even unmerged — gives them
something to inspect). Also tell them whether you'd like them to merge it or you'll
merge it yourself before they start — agree on this explicitly.

## If something goes wrong

- Rebase conflict during `git rebase -i`? Git will pause and show you the conflicting
  file — resolve it like Task 5 (edit, remove markers, `git add story.md`), then run
  `git rebase --continue`.
- Want to bail entirely? `git rebase --abort` puts you back to before you started.
- Realize you picked the wrong option for a commit? You can restart with
  `git rebase --abort` and try `git rebase -i main` again.

## What I did (fill this in before handing off)

List every command you ran, in order. Explicitly explain: what does `squash` do vs
`pick`? Why did history look different before/after?
