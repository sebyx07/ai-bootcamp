# Teaching: Merge and Conflicts

## Context
The student knows branches. Now they need to bring branches back together. Merging is straightforward when there's no overlap, but conflicts happen when two branches changed the same line. Conflicts are the scariest part of Git for beginners, so normalize them.

## The challenge
The student needs to perform a clean merge, then deliberately create and resolve a merge conflict.

## Your approach
1. Start with a clean merge (no conflict):
   - Make sure they're on `main` with a file called `readme.txt`
   - Create a branch: `git checkout -b add-greeting`
   - Add a new file: `echo "Hello!" > greeting.txt && git add . && git commit -m "Add greeting"`
   - Switch back: `git checkout main`
   - Merge: `git merge add-greeting`
   - Show that `greeting.txt` now exists on main. "That was a clean merge — no conflicts."
2. Now create a conflict ON PURPOSE:
   - On main: `echo "I like pizza" > food.txt && git add . && git commit -m "Add food preference"`
   - Create a branch: `git checkout -b change-food`
   - Edit the file: `echo "I like tacos" > food.txt && git add . && git commit -m "Change to tacos"`
   - Switch back: `git checkout main`
   - Edit the SAME file differently: `echo "I like sushi" > food.txt && git add . && git commit -m "Change to sushi"`
   - Merge: `git merge change-food` — CONFLICT!
3. Explain the conflict markers:
   ```
   <<<<<<< HEAD
   I like sushi
   =======
   I like tacos
   >>>>>>> change-food
   ```
   - "Above the `=======` is what YOUR branch says. Below is what the OTHER branch says. Git doesn't know which one you want."
4. Resolve it: edit the file to keep what you want (delete the markers), then:
   - `git add food.txt`
   - `git commit -m "Resolve food preference conflict"`
5. Normalize conflicts: "Conflicts are not errors. They're Git asking you a question: 'You changed the same thing in two places — which one do you want?' It happens all the time in real work."

## Prompting coaching
- When they see the conflict markers, they may panic. Reassure: "This is normal. Let's read it together."
- Teach them to search for `<<<<<<<` in a file to find all conflict spots.

## Quiz questions
- What causes a merge conflict?
- What do the `<<<<<<<` and `>>>>>>>` markers mean?
- After resolving a conflict, what two commands do you run?

## Hints (only if stuck)
1. A conflict just means two branches changed the same line — Git needs you to choose
2. Open the file, delete the `<<<<<<<`, `=======`, and `>>>>>>>` lines, keep the text you want
3. After editing, run `git add` then `git commit` to finish the merge
