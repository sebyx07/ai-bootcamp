# Teaching: Moving Around

## Context
The student knows where they are (pwd) and can see what's around them (ls). Now they need to MOVE — the `cd` command. This is one of the most-used commands in all of computing.

## The challenge
The student needs to navigate the file system confidently using `cd` with relative paths, absolute paths, and shortcuts.

## Your approach
1. Analogy: "Right now you're standing in one room. `cd` is how you walk to another room."
2. Start simple — have them list what's in their current folder with `ls`, then `cd` into one of those folders.
3. Teach the three essential `cd` moves:
   - `cd foldername` — go into a folder (walk forward)
   - `cd ..` — go back up one level (walk back)
   - `cd ~` — go home (teleport home)
4. Have them practice a navigation exercise:
   - Start at home (`cd ~`)
   - Go into Documents (`cd Documents`)
   - Check where you are (`pwd`)
   - Go back up (`cd ..`)
   - Check again (`pwd`)
5. Explain relative vs absolute paths:
   - Relative: `cd Documents` (from where I am now)
   - Absolute: `cd /home/yourname/Documents` (the full address)
   - Analogy: "Go to the kitchen" (relative) vs "Go to 123 Main St, Apartment 4B, Kitchen" (absolute)
6. Teach tab completion: start typing a folder name and press Tab. The terminal finishes it for you.
7. Show `cd -` to go back to the previous folder (like the "back" button).

## Prompting coaching
- Encourage them to try `cd` commands themselves in the terminal, not ask Claude to do it
- If they get lost: "Just type `cd ~` to go home and start over"

## Quiz questions
- What does `cd ..` do?
- What's the difference between `cd Documents` and `cd /home/user/Documents`?
- How do you go back to your home folder from anywhere?

## Hints (only if stuck)
1. Type `ls` first to see what folders you can `cd` into
2. If you get lost, `cd ~` always takes you home
3. Use `pwd` after every `cd` to confirm where you ended up
