# GitHub Team Exercise

An 8-person, sequential, hands-on exercise to practice real Git & GitHub workflows:
`clone`, `branch`, `commit`, `push`, pull requests, code review, **merge**,
**merge conflicts**, **rebase**, tagging, and more.

## How this works

- Everyone works on **one shared file**: [`story.md`](story.md) (a simple team story, so the *Git mechanics* are the focus, not the content).
- The tasks are **sequential** — Person 2 cannot start until Person 1 has finished and merged. This is intentional: it forces real coordination and communication, just like a real team.
- Each person has their own task file in [`tasks/`](tasks/). Read your file fully before starting.
- At the end of your task, you **must**:
  1. Post in the team channel (or however you're coordinating) that you're done and what branch/PR is ready.
  2. Tell the next person explicitly what they need to pull/branch from.
- By the end, every participant should be able to explain **every command used across all 8 tasks** — not just their own. Read each other's task files.

## Order of tasks

| # | Person | Task file | Focus |
|---|--------|-----------|-------|
| 1 | Cathrin | [tasks/01-cathrin.md](tasks/01-cathrin.md) | Repo init, first commit, push |
| 2 | Pranesh | [tasks/02-pranesh.md](tasks/02-pranesh.md) | Clone, feature branch, Pull Request |
| 3 | Sivakarthick | [tasks/03-sivakarthick.md](tasks/03-sivakarthick.md) | Code review, approve, merge PR |
| 4 | Raghul | [tasks/04-raghul.md](tasks/04-raghul.md) | Parallel branches → merge conflict (setup) |
| 5 | Srinivasan | [tasks/05-srinivasan.md](tasks/05-srinivasan.md) | Resolve merge conflict |
| 6 | Vasantharaj | [tasks/06-vasantharaj.md](tasks/06-vasantharaj.md) | Interactive rebase, clean history |
| 7 | Diwakar | [tasks/07-diwakar.md](tasks/07-diwakar.md) | Tags, CHANGELOG, log/diff/blame |
| 8 | Mrithip | [tasks/08-mrithip.md](tasks/08-mrithip.md) | Final review, squash merge, retrospective |

## Ground rules

- **Do not force-push** to `main` at any point.
- **Do not skip your task file** — even if you know Git well, the point is everyone hits the *same* situations (conflicts, rebases, PRs) so the group can compare notes.
- If you get stuck, that's normal — merge conflicts and rebases are supposed to feel a little uncomfortable the first time. Read the "If something goes wrong" section in your task file, or ask the person before you.
- When you finish, fill in the **"What I did"** section at the bottom of your own task file (command list + one-line explanation of each) before handing off. This is what makes the exercise a learning record, not just a checklist.

## Repository

Hosted at: `https://github.com/ramkumar-r-goml/github-exercise`
