# Teaching: Read and Edit Files

## Context
The student can create files and folders but they're all empty. Now they learn to put content in files and read it back. This is where the terminal starts feeling truly useful.

## The challenge
The student needs to write text into files, read files, and understand the difference between overwriting and appending.

## Your approach
1. Start with writing. Have them create a file with content:
   - `echo "Hello, world!" > greeting.txt`
   - Explain: `>` means "put this text INTO this file" (overwrites anything already there)
2. Read it back: `cat greeting.txt`
   - Explain: `cat` shows the entire file contents. Like opening a letter and reading it.
3. Teach appending:
   - `echo "How are you?" >> greeting.txt`
   - Explain: `>>` means "ADD this to the end" (doesn't erase what's already there)
   - `cat greeting.txt` to see both lines
4. IMPORTANT: Show the danger of `>` vs `>>`:
   - `echo "Oops" > greeting.txt` — this REPLACES everything!
   - `cat greeting.txt` — only "Oops" remains
   - "See? One `>` wipes the file. Two `>>` adds to it. This is a common mistake."
5. Teach reading tools for bigger files:
   - `head filename` — shows the first 10 lines
   - `tail filename` — shows the last 10 lines
   - `less filename` — lets you scroll through (press `q` to quit)
6. Practice project: Have them create a journal file and write 3 entries using `>>`.

## Prompting coaching
- If they ask "how do I edit a file?", teach `echo` with `>` and `>>` first — it's simpler than opening an editor
- Also introduce `nano` briefly — it's a simple terminal text editor they'll need later (especially on remote servers)
- Show them: `nano greeting.txt` — edit the file, Ctrl+O to save, Ctrl+X to exit
- Don't go deep on nano now — just enough so they know it exists and can use it in a pinch

## Quiz questions
- What's the difference between `>` and `>>`?
- What does `cat` do?
- If you run `echo "new" > file.txt` on a file that already has content, what happens?

## Hints (only if stuck)
1. Try `echo "test" > myfile.txt` then `cat myfile.txt` to see it work
2. Remember: one arrow `>` replaces, two arrows `>>` adds
3. Use `cat` after every change to see what your file looks like now
