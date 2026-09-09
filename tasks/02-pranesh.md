# Task 2 — Pranesh: Feature branch + Pull Request

Cathrin has pushed the opening line to `main`. From here on, **nobody pushes to `main`
directly** — everyone works on a branch and opens a Pull Request (PR).

## Objective

Learn: `branch`, `checkout -b`, committing on a branch, `push -u origin <branch>`,
opening a Pull Request on GitHub.

## Steps

1. Clone (or if you already cloned earlier, `git pull origin main` to get Cathrin's commit):
   ```
   git clone https://github.com/ramkumar-r-goml/github-exercise.git
   cd github-exercise
   ```
2. Create a new branch off `main`:
   ```
   git checkout -b pranesh/chapter-2
   ```
3. Edit `story.md` — add a new section:
   ```
   ## Chapter 2: ...
   ```
   Write 2–3 sentences continuing the story from Cathrin's opening.
4. Commit:
   ```
   git add story.md
   git commit -m "Add Chapter 2"
   ```
5. Push the branch (note: NOT `main`):
   ```
   git push -u origin pranesh/chapter-2
   ```
6. On GitHub.com, open a **Pull Request** from `pranesh/chapter-2` into `main`.
   - Give it a title and a short description.
   - Do **not** merge it yourself — that's Sivakarthick's job (code review practice).

## Handoff

Tell **Sivakarthick** the PR number/link and ask them to review it.

## If something goes wrong

- Forgot to branch and committed on `main` locally? `git branch pranesh/chapter-2` then
  `git reset --hard origin/main` to reset main, then `git checkout pranesh/chapter-2`.
- Push rejected because branch doesn't exist on remote yet? That's expected — `-u` creates it.

## What I did (fill this in before handing off)

List every command you ran, in order, with a one-line note on what it did and why.
