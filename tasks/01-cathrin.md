# Task 1 — Cathrin: Repo setup, first commit, push

You're up first. There's nothing to pull yet — this repo already exists on GitHub
(`ramkumar-r-goml/github-exercise`) with a `story.md` and this `tasks/` folder.
Your job is to make the **first real contribution** to the story directly on `main`.

## Objective

Learn: `clone`, `status`, `add`, `commit`, `push`, `log`.

## Steps

1. Clone the repo (don't skip this even if you think you have it already — everyone should clone fresh):
   ```
   git clone https://github.com/ramkumar-r-goml/github-exercise.git
   cd github-exercise
   ```
2. Check the repo state:
   ```
   git status
   git log --oneline
   ```
3. Open `story.md` and replace the `_(waiting for the first contribution...)_` line with
   1–2 sentences starting the story. Keep it short — content doesn't matter, the workflow does.
4. Stage and commit:
   ```
   git add story.md
   git commit -m "Start the story"
   ```
5. Push directly to `main` (this is the only task in the whole exercise where pushing
   straight to `main` is allowed — everyone else must use a branch + PR):
   ```
   git push origin main
   ```
6. Confirm on GitHub.com that your commit shows up on `main`.

## Handoff

Tell **Pranesh** that `main` is ready and has your opening line in `story.md`. Give them
the repo URL if they don't have it.

## If something goes wrong

- `git push` rejected? Run `git pull origin main` first, then push again.
- Wrong commit message? `git commit --amend -m "new message"` — but only before you push.

## What I did (fill this in before handing off)

List every command you actually ran, in order, with a one-line note on what it did and why.
Example format:

```
git clone <url>       -> got a local copy of the repo
git status             -> checked what's changed / untracked
...
```
