# Task 8 — Mrithip: Final review, squash merge, retrospective

You're last. `main` has 4 chapters, a CHANGELOG, and a `v1.0.0` tag. Your job is to
add the closing chapter, practice one more merge strategy (**squash merge**, different
from the merge commits used earlier), and write the exercise retrospective.

## Objective

Learn: `squash merge` (and how it differs from a regular merge commit), reviewing an
entire repo's history end-to-end, closing out a collaborative exercise.

## Steps

1. Sync:
   ```
   git checkout main
   git pull origin main
   ```
2. Branch and write the final chapter:
   ```
   git checkout -b mrithip/chapter-5-finale
   ```
   Add `## Chapter 5: The Finale` to `story.md` with a short closing to the story.
3. Commit (2-3 small commits is fine, doesn't need to be squashed manually this time —
   that's what the merge strategy is for):
   ```
   git add story.md
   git commit -m "Add finale heading"
   # ...more edits...
   git add story.md
   git commit -m "Finish story finale"
   ```
4. Push and open a PR:
   ```
   git push -u origin mrithip/chapter-5-finale
   ```
5. This time, merge using **"Squash and merge"** on GitHub (not "Create a merge
   commit"). Notice this collapses all your commits into a single commit on `main`,
   unlike Sivakarthick's or Raghul's merges earlier which kept a merge commit and
   individual commits visible. Delete the branch after.
6. Sync and look at the final history:
   ```
   git checkout main
   git pull origin main
   git log --oneline --graph --all
   ```
   Compare this graph to what you saw description of in Task 7 (Diwakar's step 2) —
   you should be able to spot the merge commits (Tasks 3, 4, 5) vs. this squashed one.
7. Tag the final version:
   ```
   git tag -a v1.1.0 -m "Story complete with finale"
   git push origin v1.1.0
   ```
8. Write a short **retrospective** at the bottom of the root [README.md](../README.md),
   under a new `## Retrospective` heading: one sentence per person on what Git/GitHub
   feature they practiced and one thing that felt confusing or clicked for them (ask
   each teammate for their one-liner, or use what they wrote in their own task file's
   "What I did" section).
9. Commit this directly to `main` via one more small branch+PR+merge cycle (your
   choice of merge strategy this time — pick whichever you understand best and note
   why in your own "What I did" below).

## Handoff

Post in the team channel: exercise complete, link the repo, link `v1.1.0`, and ask
everyone to make sure their own task file's "What I did" section is filled in — that's
the actual deliverable proving everyone understands the commands, not just the story
content.

## If something goes wrong

- Squash merge conflict on GitHub? Same idea as Task 5 — pull latest `main` locally,
  `git merge origin/main` on your branch, resolve, push, retry the squash merge.

## What I did (fill this in before handing off)

List every command you ran, in order. Explain in your own words: squash merge vs.
merge commit — when would you use each in a real team?

---

## Facilitator check (Mrithip, last step)

Before calling this done, confirm every file in `tasks/` has its "What I did" section
filled in by the right person. If someone's is empty, ping them — the exercise isn't
complete until all 8 are filled in.
