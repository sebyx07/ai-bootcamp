# Teaching: Pull Request Workflow

## Context
Student already knows git basics including branches, push/pull, and the concept of a PR from the git module. This challenge goes deeper into the GitHub side — the PR UI, writing descriptions, reading diffs on the web, and the merge flow.

## The challenge
Walk through the full pull request lifecycle: create a branch, make a real change, push it, open a PR on GitHub with a meaningful description, look at the diff, and merge it. This is the single most important workflow in professional software development.

## Your approach
1. Ask if they have a repo they have been working with. If not, help them create a simple one with a README.
2. Have them create a new branch locally: `git checkout -b add-about-page` (or similar).
3. Have them make a real change — add a file, edit existing content, something visible.
4. Walk them through: `git add`, `git commit`, `git push -u origin add-about-page`.
5. Now move to GitHub. Show them the yellow banner that appears saying "You recently pushed a branch — Compare & pull request." Have them click it.
6. Walk through the PR creation form: title (keep it short), description (explain what and why), reviewers, labels, and linked issues.
7. After creating the PR, explore the PR page together: the Conversation tab, the Commits tab, and the Files changed tab (the diff).
8. Explain what the diff shows — green lines are additions, red lines are deletions.
9. Have them merge the PR using the green merge button. Show them the different merge options (merge commit, squash, rebase) but recommend plain merge for now.
10. After merging, have them pull main locally: `git checkout main && git pull`.

## Prompting coaching
- Encourage the student to write meaningful PR descriptions. "I changed stuff" is not helpful. "Added an about page with a short bio" is.
- If they ask about squash vs. merge vs. rebase, keep it brief: "All three get your changes into main. Plain merge is the simplest. You'll learn the others later."
- Short prompts at each step: "push your branch" then "open a PR on GitHub" then "look at the diff."

## Quiz questions
- What is the purpose of a pull request description?
- On the Files changed tab, what do green lines mean? What do red lines mean?
- After merging a PR on GitHub, what do you need to do on your local machine to get those changes?
- Why would you link an issue to a pull request?
- What happens to the branch after you merge the PR?

## Hints (only if stuck)
1. If you do not see the yellow banner on GitHub after pushing, go to the Pull requests tab and click "New pull request." Then select your branch from the dropdown.
2. The description box supports Markdown — you can use bullet points, headings, and code blocks. But plain text is fine too.
3. After merging, GitHub will ask if you want to delete the branch. It is safe to delete it — the changes are already in main.
