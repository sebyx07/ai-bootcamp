# Teaching: Daily Git Workflow

## Context
The student has learned all the individual Git pieces. This challenge puts them together into the daily workflow they'll actually use. It's a capstone exercise — practice the real routine until it feels natural.

## The challenge
The student needs to perform the complete professional Git workflow from start to finish, multiple times, until it becomes muscle memory.

## Your approach
1. Present "The Daily Workflow" as a checklist:
   ```
   1. git pull                          (get latest changes)
   2. git checkout -b my-feature        (create a branch for your work)
   3. ... make your changes ...
   4. git add .                         (stage changes)
   5. git commit -m "Describe changes"  (save a snapshot)
   6. git push -u origin my-feature     (push to GitHub)
   7. Open a pull request on GitHub
   8. Get it reviewed and merged
   9. git checkout main                 (go back to main)
   10. git pull                         (get the merged changes)
   ```
2. Have them run through this entire cycle at least twice with different features.
3. Teach `git stash` — for when you need to switch branches but aren't ready to commit:
   - "Imagine you're cooking and someone calls. You put your ingredients in the fridge (stash) and deal with the call. Then you take them out and continue."
   - `git stash` — save work temporarily
   - `git stash list` — see your stashed work
   - `git stash pop` — bring it back
4. Teach `.gitignore` — what NOT to commit:
   - Create a `.gitignore` file
   - Explain: "Some files should NEVER go to GitHub — passwords, secrets, huge files, OS junk"
   - Common entries:
     ```
     node_modules/
     .env
     *.log
     .DS_Store
     tmp/
     ```
   - "Every real project has a .gitignore. It's one of the first files you create."
   - Show that ignored files don't appear in `git status`
5. Teach useful shortcuts:
   - `git add -A` — add ALL changes (including deletions)
   - `git commit -am "message"` — add and commit tracked files in one step
   - `git log --oneline -5` — see the last 5 commits
5. Have them create a Git cheat sheet file in their project:
   - Create `git-cheatsheet.txt`
   - Write their most-used commands with short descriptions
   - Commit and push it — practice the workflow WITH the cheat sheet
6. End with: "You now know how professional developers use Git every day. This exact workflow is what you'll do at any tech company."

## Prompting coaching
- At this point, encourage them to type commands themselves rather than asking Claude
- If they ask for a command, give it but also say: "Try to remember this one — you'll use it daily"
- Praise their progress: "You went from 'what is Git' to a full professional workflow."

## Quiz questions
- Walk me through the daily Git workflow from start to finish.
- When would you use `git stash`?
- What's the first thing you do in the morning when starting work on a project?

## Hints (only if stuck)
1. Start with `git pull` to get the latest, then create a branch
2. The cycle is: pull, branch, code, add, commit, push, PR, merge, pull
3. If you forget a command, check your cheat sheet — that's what it's for
