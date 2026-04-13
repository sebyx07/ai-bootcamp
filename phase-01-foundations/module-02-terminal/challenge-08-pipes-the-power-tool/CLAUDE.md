# Teaching: Pipes — The Power Tool

## Context
The student knows individual commands. Pipes let them COMBINE commands, which is what makes the terminal truly powerful. This is often the "aha moment" for beginners — when they see that simple tools chained together can do complex things.

## The challenge
The student needs to learn pipes (`|`) and practice combining commands to solve real problems.

## Your approach
1. Analogy: "Imagine an assembly line in a factory. Each station does one thing, then passes the result to the next station. That's a pipe."
2. Start with a concrete example. Create a file with names:
   ```
   echo -e "Charlie\nAlice\nBob\nDavid\nAlice\nBob" > names.txt
   ```
3. Show the problem: "I want to see this list sorted, without duplicates, and know how many unique names there are."
4. Build it up step by step:
   - `cat names.txt` — see the list
   - `cat names.txt | sort` — see it sorted
   - `cat names.txt | sort | uniq` — remove duplicates
   - `cat names.txt | sort | uniq | wc -l` — count the unique names
5. Explain: "The `|` symbol takes the output of one command and feeds it as input to the next. Each command does one small job."
6. Teach useful pipe partners:
   - `sort` — sorts lines alphabetically
   - `uniq` — removes duplicate adjacent lines (that's why you sort first)
   - `wc -l` — counts lines
   - `head -5` — takes only the first 5 lines
   - `grep "pattern"` — filters to only matching lines
7. Real-world exercise: Create a file with 20 lines of server log-like entries. Have them use pipes to:
   - Find all lines containing "ERROR"
   - Count how many errors there are
   - `grep "ERROR" log.txt | wc -l`
8. Challenge them: "Using pipes, find the 3 most common words in a file." (Advanced, but fun to try.)

## Prompting coaching
- Pipes look intimidating at first. Teach them to build left to right: start with one command, add a pipe and the next, test, repeat.
- "If you're not sure what a pipe chain does, run just the first part, then add the next pipe."

## Quiz questions
- What does the `|` symbol do?
- What does `cat file.txt | sort | head -3` do?
- Why do you need `sort` before `uniq`?

## Hints (only if stuck)
1. The pipe symbol `|` is usually on the same key as backslash `\` (press Shift)
2. Start with just `cat filename.txt`, then add `| sort` to the end
3. Think of it as a chain: each link does one thing and passes the result forward
