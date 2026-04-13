# Teaching: Branches

## Context
The student has been making commits on one straight line. Branches introduce the idea of parallel timelines — working on something new without touching what already works. This is a conceptual leap, so analogies are critical.

## The challenge
The student needs to create branches, switch between them, and see that changes on one branch don't affect another.

## Your approach
1. Analogy: "Imagine you're writing a book. Branches are like making a copy of your manuscript to try a different ending. Your original is safe while you experiment."
2. Another analogy: "Think of branches as parallel universes. In one universe, you add a new feature. In another, the old version continues untouched. You can hop between universes."
3. Make sure they have a project with a few commits. Then:
   - `git branch` — see all branches (there's just `main` or `master`)
   - `git checkout -b add-feature` — create AND switch to a new branch
   - Explain: "-b means 'create this branch'. Without it, you just switch."
4. On the new branch, make changes and commit:
   - Create a new file: `echo "New feature!" > feature.txt`
   - `git add feature.txt && git commit -m "Add new feature"`
5. Switch back and show the magic:
   - `git checkout main`
   - `ls` — feature.txt is GONE! "It only exists on the other branch."
   - `git checkout add-feature`
   - `ls` — feature.txt is BACK!
6. This is usually the "whoa" moment. Let them sit with it.
7. Have them create a second branch and make different changes.
8. Show `git log --oneline --all --graph` to visualize the branches.
9. Mention `git switch` as the newer alternative to `git checkout` for switching branches.

## Prompting coaching
- If they're confused about which branch they're on: "Run `git branch` — the star (*) shows your current branch."
- Remind them that `git status` also shows the current branch at the top.

## Quiz questions
- What happens to files when you switch branches?
- How do you create a new branch and switch to it in one command?
- If you make a commit on branch "experiment", can you see it from branch "main"?

## Hints (only if stuck)
1. `git checkout -b branchname` creates and switches to a new branch
2. `git checkout main` takes you back to the main branch
3. Use `git branch` to see which branch you're on (look for the star)
