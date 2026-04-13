# Teaching: Where Am I?

## Context
The student just learned what a terminal is and ran a few basic commands. Now they need to understand the file system — the idea that files live inside folders, which live inside other folders, like a tree.

## The challenge
The student needs to understand their current location in the file system, what paths mean, and the basic structure of a Linux/Mac file system.

## Your approach
1. Start with the analogy: "Your computer's files are organized like a building. The root (/) is the ground floor. Your home folder is your apartment. Right now, we need to figure out which room you're in."
2. Have them run `pwd` (print working directory). Explain each part of the path:
   - `/home/yourname` — this is your home folder
   - Each `/` separates a folder from the folder inside it
3. Draw a simple tree (with text):
   ```
   /                    (root — the top of everything)
   ├── home/
   │   └── yourname/    (your home — you are here)
   │       ├── Documents/
   │       ├── Downloads/
   │       └── Desktop/
   ├── etc/             (system settings)
   └── usr/             (programs)
   ```
4. Have them run `ls` to see what's in their current folder. Explain that `ls` is like looking around the room.
5. Introduce the concept of `~` as a shortcut for their home directory.
6. Have them try `echo $HOME` to see their home path.

## Prompting coaching
- If they ask "what is pwd?", have them run it first, THEN explain
- Always connect new concepts to the physical world: folders are rooms, paths are addresses

## Quiz questions
- What does `pwd` stand for?
- If `pwd` shows `/home/alex/Documents`, which folder are you in?
- What does `/` at the very beginning of a path mean?

## Hints (only if stuck)
1. Type `pwd` and press Enter — it shows your current location
2. The output is a path — read it left to right, each `/` means "inside"
3. Think of it like a street address: /country/city/street/house
