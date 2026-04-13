# Teaching: Know When to Type Yourself

## Context
The student has been relying on Claude for everything. That's fine for learning, but they need to start building independence. This challenge teaches judgment: when is AI help valuable vs. when is it overhead?

## The challenge
The student needs to identify situations where typing a command themselves is faster or better than asking Claude, and practice doing both.

## Your approach
1. Start by being honest: "I'm going to teach you something important — when NOT to use me."
2. Demonstrate the overhead. Ask them to time two approaches:
   - Ask Claude: "Show me what folder I'm in" (requires typing, waiting, reading)
   - Type it yourself: `pwd` (instant)
3. Give them a list of tasks and ask them to sort into "Claude helps" vs. "do it yourself":
   - Checking what folder you're in (yourself: `pwd`)
   - Listing files (yourself: `ls`)
   - Writing a 20-line configuration file (Claude)
   - Renaming a file (yourself, once you know `mv`)
   - Explaining what an error message means (Claude)
   - Creating a project with 5 files and specific content (Claude)
   - Deleting a file (yourself: `rm filename`)
4. Teach them a few basic commands they can type right now:
   - `pwd` — where am I?
   - `ls` — what's here?
   - `clear` — clean the screen
5. Have them practice these commands outside of Claude Code (in a regular terminal).
6. End with the rule of thumb: "If you can say it in 3 words, try typing the command. If you need to think about it, ask me."

## Prompting coaching
- This is about knowing when NOT to prompt
- Teach them: "The best developers use AI for hard things and their own hands for easy things"
- Emphasize that learning commands yourself makes you faster overall

## Quiz questions
- Is it faster to ask Claude "what folder am I in?" or type `pwd`?
- Name two tasks where Claude is genuinely more helpful than doing it yourself.
- Why is it important to learn some commands yourself even though Claude can do them?

## Hints (only if stuck)
1. Open a separate terminal window (not Claude Code) and try typing `pwd`
2. Simple commands like `ls` and `pwd` are always faster to type yourself
3. Ask Claude for help with anything that requires thinking or writing multiple lines
