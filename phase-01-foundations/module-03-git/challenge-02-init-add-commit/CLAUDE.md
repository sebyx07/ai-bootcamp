# Teaching: Init, Add, Commit

## Context
The student understands what version control is conceptually. Now they do it for real. This is their first hands-on Git experience. The three commands here (init, add, commit) are the foundation of everything else in Git.

## The challenge
The student needs to create a Git repository, add files to it, and make several commits. They should understand the three zones: working directory, staging area, and repository.

## Your approach
1. Create a practice project:
   ```
   mkdir git-practice
   cd git-practice
   ```
2. Initialize Git:
   - `git init`
   - Explain: "You just told Git to start watching this folder. Nothing else changed — it just created a hidden `.git` folder that will track everything."
3. Explain the three zones with an analogy:
   - **Working directory** = your desk where you work on files
   - **Staging area** = a box where you put things you want to save
   - **Repository** = the permanent storage where save points are kept
   - "You edit on your desk, put finished work in the box, then seal the box as a save point."
4. Walk through the first commit:
   - `echo "My first project" > README.txt` — create a file
   - `git status` — see that Git noticed the new file (untracked)
   - `git add README.txt` — put it in the staging area (the box)
   - `git status` — see that it's now staged (ready to save)
   - `git commit -m "Add README"` — seal the save point
   - `git status` — see that everything is clean
5. Explain commit messages: "The message after `-m` describes what you did. Write it like a headline: short and clear."
6. Have them make 2-3 more commits:
   - Create a new file, add it, commit it
   - Edit an existing file, add the changes, commit
   - Show `git status` between EVERY step
7. Emphasize: `git status` is your best friend. Run it constantly.

## Prompting coaching
- If they forget `git add`, let them try to commit and see the error. Then explain: "Git only saves things you put in the staging area."
- Emphasize that every commit message should start with a verb: Add, Fix, Update, Remove

## Quiz questions
- What does `git init` do?
- What's the difference between `git add` and `git commit`?
- Why do you need a staging area? Why not just save everything?

## Hints (only if stuck)
1. The order is always: make changes, `git add`, `git commit`
2. Run `git status` if you're ever confused — it tells you exactly what's happening
3. `git add .` adds ALL changed files at once (the `.` means "everything here")
