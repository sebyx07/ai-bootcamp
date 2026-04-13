# Teaching: Pull Requests

## Context
The student can push code to GitHub. Pull requests (PRs) are how real teams work — instead of pushing directly to the main branch, you create a branch, push it, and ask someone to review it before merging. This is a workflow lesson as much as a technical one.

## The challenge
The student needs to create a pull request on GitHub, understand its purpose, and merge it.

## Your approach
1. Explain the concept: "In a real team, you don't push directly to main. Instead, you say: 'Hey, I made some changes on a branch. Can someone look at them before we merge?' That request is called a Pull Request — or PR."
2. Walk through the full workflow:
   - Start on main: `git checkout main && git pull`
   - Create a branch: `git checkout -b improve-readme`
   - Make a change: edit README.txt or create a new file
   - Commit: `git add . && git commit -m "Improve the README with more details"`
   - Push the branch: `git push -u origin improve-readme`
3. Create the PR:
   - Option A (GitHub CLI): `gh pr create --title "Improve README" --body "Added more details to the README file"`
   - Option B (Web): Go to GitHub, click the "Compare & pull request" button that appears
4. Show them the PR page on GitHub:
   - The title and description
   - The "Files changed" tab — shows exactly what was modified
   - The merge button
5. Have them merge it on GitHub (click "Merge pull request").
6. Back locally:
   - `git checkout main`
   - `git pull` — now main has the merged changes
7. Explain why PRs matter:
   - Code review: someone else can check your work
   - Discussion: you can leave comments and ask questions
   - Safety: main stays stable because nothing goes in without review

## Prompting coaching
- PRs can feel like bureaucracy to beginners. Emphasize the value: "PRs catch mistakes before they reach everyone."
- If they use `gh pr create`, show them the web interface too — they should be comfortable with both.

## Quiz questions
- What is a pull request?
- Why don't teams push directly to the main branch?
- After merging a PR on GitHub, what command do you run locally to get the changes?

## Hints (only if stuck)
1. Make sure you pushed your branch first: `git push -u origin branchname`
2. Go to your repo on GitHub.com — there should be a yellow banner offering to create a PR
3. After merging on GitHub, run `git checkout main && git pull` locally
