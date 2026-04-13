# Teaching: See Your History

## Context
The student has made several commits. Now they need to look backward — see what they've done, when they did it, and what exactly changed. This is where Git's value becomes tangible: "I can see everything I've ever done."

## The challenge
The student needs to read commit history with `git log` and see specific changes with `git diff`.

## Your approach
1. Make sure they have a project with at least 3-4 commits (from the previous challenge or create new ones).
2. Teach `git log`:
   - `git log` — shows full history (press `q` to exit)
   - Point out the parts: commit hash, author, date, message
   - `git log --oneline` — the compact version (one line per commit)
   - `git log --oneline --graph` — shows branch structure visually
3. Teach `git diff`:
   - Edit a file but DON'T commit yet
   - `git diff` — shows what changed (red = removed, green = added)
   - Explain the output: "Lines starting with `-` were removed. Lines starting with `+` were added."
   - `git diff --staged` — shows changes that are already staged
4. Teach `git show`:
   - `git show HEAD` — see the most recent commit's details
   - Copy a commit hash from `git log --oneline` and use `git show <hash>`
5. Practice exercise: Have them make 3 more commits with different changes, then use `git log --oneline` to see the timeline. Ask: "Can you find the commit where you added [specific thing]?"
6. Show them that EVERY change is recorded: "This is why commit messages matter. Good messages make it easy to find things later."

## Prompting coaching
- If `git log` seems overwhelming, always suggest `git log --oneline` first
- Teach them that `q` exits the log viewer (many beginners get stuck here)

## Quiz questions
- What command shows your commit history?
- What does the commit hash (that long string of letters and numbers) represent?
- What does `git diff` show you?

## Hints (only if stuck)
1. Type `git log --oneline` for the simplest view of your history
2. Press `q` to exit the log if it takes over your screen
3. Edit a file, then run `git diff` BEFORE committing to see the changes highlighted
