# Teaching: PATH Issues

## Context
The student has encountered PATH indirectly throughout this phase (NVM and rbenv both modify PATH). This is the deep dive. PATH is the invisible variable behind most "command not found" errors, version conflicts, and "it works in one terminal but not another" mysteries. Understanding PATH is a superpower.

## The challenge
Understand how PATH works, break it intentionally, fix it, and learn to modify it safely.

## Your approach

### Step 1: Understand PATH
1. Start by asking: "When you type `node` in the terminal, how does the computer know where the `node` program is?"
2. Have them run: `echo $PATH`
3. Explain: "This is a list of directories, separated by colons. When you type a command, your shell searches each directory in order. The first match wins."
4. Demonstrate with `which`:
   - `which node` — shows where node lives
   - `which ruby` — shows where ruby lives
   - `which ls` — even basic commands are found via PATH
5. Show the order matters:
   - `echo $PATH | tr ':' '\n'` — shows each directory on its own line
   - "If there were two versions of `node` in different directories, the one in the directory listed FIRST would win."

### Step 2: Break PATH intentionally
6. Create a broken scenario (in the CURRENT shell only -- this is safe):
   ```
   # Save the original PATH
   ORIGINAL_PATH=$PATH
   # Break it
   export PATH="/usr/bin"
   ```
7. Now have them try commands:
   - `ls` — still works (it is in /usr/bin)
   - `node` — command not found!
   - `ruby` — command not found!
   - `docker` — might or might not work depending on where it is installed
8. Ask: "What happened? Why did some commands stop working?"
9. They should realize: the directories containing node and ruby are no longer in PATH.

### Step 3: Fix PATH
10. Restore it: `export PATH=$ORIGINAL_PATH`
11. Verify everything works again.
12. Teach the safe way to ADD to PATH:
    ```
    export PATH="$PATH:/new/directory"
    ```
    "Always include `$PATH` so you do not lose everything else."

### Step 4: Make it permanent
13. Explain that `export` only affects the current terminal session.
14. To make it permanent, add it to `~/.bashrc`:
    ```
    echo 'export PATH="$PATH:/new/directory"' >> ~/.bashrc
    ```
15. Show them what NVM and rbenv added to their `~/.bashrc`:
    ```
    grep -A 2 'NVM_DIR\|rbenv' ~/.bashrc
    ```
16. Connect the dots: "This is why we had to run `source ~/.bashrc` after installing NVM. It added PATH modifications to this file."

### Step 5: A real-world PATH puzzle
17. Create a custom script:
    ```
    mkdir -p ~/bin
    echo '#!/bin/bash' > ~/bin/greet
    echo 'echo "Hello from ~/bin!"' >> ~/bin/greet
    chmod +x ~/bin/greet
    ```
18. Try running it: `greet` -- command not found.
19. Ask: "Why?" (~/bin is not in PATH)
20. Fix it: `export PATH="$PATH:$HOME/bin"` then `greet` works.
21. Make it permanent by adding to `~/.bashrc`.

### Cleanup
```
rm -rf ~/bin/greet
# Remove the PATH line we added to .bashrc if desired
```

## Prompting coaching
- Teach: "Explain PATH like I have never heard of it."
- Encourage: "I installed something but the terminal cannot find it. How do I fix my PATH?"
- Model: "How do I see my current PATH in a readable format?"

## Quiz questions
- What is the PATH variable?
- If you have two programs named `python` in different directories, which one runs when you type `python`?
- What is the difference between adding to PATH with `export` vs adding it to `~/.bashrc`?
- Why should you NEVER set PATH without including `$PATH` (the old value)?
- How did NVM and rbenv modify your PATH?

## Hints (only if stuck)
1. `echo $PATH | tr ':' '\n'` makes PATH readable.
2. `which <command>` tells you exactly which file runs when you type a command.
3. If you accidentally destroyed your PATH, just close the terminal and open a new one. Your `~/.bashrc` will restore it.
