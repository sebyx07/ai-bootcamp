# Teaching: Install Something Useful

## Context
The student knows apt basics and understands the concept of package managers. Now they need practice and confidence. This challenge is about building muscle memory and showing them that the command line is not just for developers -- it has genuinely useful tools.

## The challenge
Search for, install, and use at least 3 useful command-line tools from a curated list.

## Your approach
1. Present a menu of useful packages and let them choose:
   - `htop` — interactive process viewer (like Task Manager but better)
   - `tree` — shows directory structure as a tree
   - `curl` — downloads files and makes web requests
   - `jq` — formats and filters JSON data
   - `tldr` — simplified man pages with practical examples
   - `ncdu` — disk usage analyzer
   - `bat` — like `cat` but with syntax highlighting
   - `ripgrep` (package: `ripgrep`) — super fast text search
   - `neofetch` — displays system info in a cool way
2. Ask: "Which of these sound interesting to you? Pick at least 3."
3. For each one they choose:
   - Have them install it with `sudo apt install <package>`
   - Show them how to use it with a practical example
   - Let them experiment with it
4. After installing their choices, have them run `apt list --installed | tail -20` to see recently installed packages.
5. Show them `dpkg -l | grep <package>` as another way to check if something is installed.

## Prompting coaching
- Teach them to ask: "What are the most useful command-line tools I should know about?"
- Show them that `apt search <keyword>` is a way to discover tools.
- Encourage: "Show me how to use this tool with a real example."

## Quiz questions
- How would you search for a package if you do not know its exact name?
- How can you check if a package is already installed?
- What command shows you information about a package before you install it?

## Hints (only if stuck)
1. Start with `neofetch` -- it is the most visually rewarding and easiest to use.
2. Use `apt search <keyword>` to find packages related to what you want.
3. If a package name does not work, try searching for it -- the package name is not always the same as the command name.
