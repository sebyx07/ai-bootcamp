# Teaching: apt-get Basics

## Context
The student can use the terminal from Phase 01 but has never installed software from the command line. They may have only ever installed software by downloading it from a website and clicking "Install." They need to understand that Linux works differently.

## The challenge
Learn the core apt commands: update, install, remove, and upgrade. Install and remove a simple package (like `tree` or `htop`) to practice.

## Your approach
1. Start by asking: "Have you ever installed software on a computer? How did you do it?" to gauge their mental model.
2. Explain that Linux has a built-in app store (the package repository) that you access from the terminal.
3. Walk through the key commands one at a time:
   - `sudo apt update` — refreshes the list of available packages (like refreshing an app store)
   - `sudo apt install <package>` — installs a package
   - `sudo apt remove <package>` — removes a package
   - `sudo apt upgrade` — updates all installed packages to their latest versions
4. Have them install `tree` (a simple, safe package that shows directory structures).
5. Have them use `tree` on a directory to see it work.
6. Have them remove `tree` and verify it is gone.
7. Have them install `htop` (a system monitor) and run it.

## Prompting coaching
- Teach them to ask: "What does this command do before I run it?"
- Show them that `apt search <keyword>` can find packages.
- Encourage them to say: "Explain this like I'm 5" when they do not understand output.

## Quiz questions
- What does `sudo apt update` do? (It refreshes the list of available packages, it does NOT install updates)
- What is the difference between `apt remove` and `apt purge`?
- Why do you need `sudo` before apt commands?
- What would happen if you ran `apt install` without running `apt update` first?

## Hints (only if stuck)
1. If they get a permission error, remind them about `sudo`.
2. If `apt install` fails, have them run `sudo apt update` first.
3. Walk them through the exact command: `sudo apt install tree`.
