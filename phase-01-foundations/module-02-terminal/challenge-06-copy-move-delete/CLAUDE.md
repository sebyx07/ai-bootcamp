# Teaching: Copy, Move, Delete

## Context
The student can create files and write to them. Now they need to manage files — copying, moving, renaming, and deleting. The delete command needs extra care because there's no recycle bin in the terminal.

## The challenge
The student needs to practice copying, moving, renaming, and deleting files and folders from the command line.

## Your approach
1. Set up a practice area first:
   ```
   mkdir practice-area
   cd practice-area
   echo "important stuff" > original.txt
   echo "notes here" > notes.txt
   mkdir backup
   ```
2. Teach `cp` (copy):
   - `cp original.txt copy-of-original.txt` — makes a duplicate
   - `cp original.txt backup/` — copies into the backup folder
   - `cp -r foldername newfoldername` — copies a whole folder (`-r` means recursive)
3. Teach `mv` (move AND rename — same command!):
   - `mv notes.txt backup/` — moves the file to the backup folder
   - `mv original.txt better-name.txt` — renames the file
   - "Moving and renaming are the same thing to a computer — you're just changing where the file lives."
4. Teach `rm` (delete) with a WARNING:
   - "This is the one command where you need to be careful. `rm` deletes forever. There is no trash can. There is no undo."
   - `rm copy-of-original.txt` — deletes the file
   - `rm -r foldername` — deletes a folder and everything inside
   - NEVER teach `rm -rf /` or anything close to it
5. Teach `chmod` (file permissions) basics:
   - `ls -l` — shows permissions like `-rw-r--r--`
   - Explain the three groups: owner, group, everyone
   - `chmod +x script.sh` — makes a file executable
   - `chmod 644 file.txt` — read/write for owner, read-only for others
   - "You'll see permission errors sometimes — `chmod` is how you fix them"
6. Practice exercise: Have them organize a messy folder — create 5 files, then sort them into subfolders using `mv`, make backups with `cp`, and clean up extras with `rm`. Then make one file executable with `chmod`.

## Prompting coaching
- Emphasize: "Before running `rm`, double-check the filename. Read it twice."
- Teach the habit of using `ls` before `rm` to make sure you're deleting the right thing

## Quiz questions
- How do you rename a file in the terminal?
- What's the difference between `cp` and `mv`?
- Why is `rm` different from dragging a file to the trash?

## Hints (only if stuck)
1. `cp source destination` — always source first, destination second
2. `mv` works the same way — `mv oldname newname` to rename
3. Start with `ls` to see what files you have before copying or deleting
