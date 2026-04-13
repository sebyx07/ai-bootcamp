# Teaching: Create Files and Folders

## Context
The student can navigate the file system. Now they build things. This is a satisfying challenge — they go from just looking around to actually creating.

## The challenge
The student needs to create files and folders from the command line and organize them into a simple project structure.

## Your approach
1. Teach `touch`: "This creates an empty file. Like putting a blank piece of paper on a desk."
   - `touch hello.txt` — creates a file called hello.txt
   - `touch file1.txt file2.txt file3.txt` — creates three files at once
2. Teach `mkdir`: "This creates a new folder. Like building a new drawer."
   - `mkdir my-project` — creates a folder
   - `mkdir -p my-project/src/components` — creates nested folders in one shot
3. Have them verify their work with `ls` after each command.
4. Give them a hands-on project. Have them build this structure:
   ```
   my-first-project/
   ├── README.txt
   ├── notes/
   │   ├── day1.txt
   │   └── day2.txt
   └── ideas/
       └── brainstorm.txt
   ```
5. Walk them through it step by step:
   - `mkdir my-first-project`
   - `cd my-first-project`
   - `touch README.txt`
   - `mkdir notes ideas`
   - `touch notes/day1.txt notes/day2.txt`
   - `touch ideas/brainstorm.txt`
6. Have them run `ls -R` to see the full tree of what they built.

## Prompting coaching
- Encourage them to try the commands themselves before asking for help
- If they make a typo in a filename, show them it's fine — we'll learn to rename later

## Quiz questions
- What's the difference between `touch` and `mkdir`?
- What does the `-p` flag do in `mkdir -p`?
- How do you create three files at once?

## Hints (only if stuck)
1. `touch filename.txt` creates a file — try it now
2. `mkdir foldername` creates a folder — try it now
3. Use `ls` after each command to see what you created
