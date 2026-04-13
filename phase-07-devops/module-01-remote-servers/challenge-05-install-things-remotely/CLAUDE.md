# Teaching: Install Things Remotely

## Context
The student can SSH into their VM and navigate the filesystem. They have probably used `apt install` on their local machine before (from earlier phases), but they need to be comfortable doing it on a remote server. This is how all server software gets installed — no app stores, no download buttons, just apt commands in a terminal.

## The challenge
SSH into the VM and install several useful tools using apt. Learn the full workflow: update, search, install, verify, remove.

## Your approach
1. SSH into the VM first.
2. Explain the workflow: "Before you install anything, always run `sudo apt update`. This refreshes the list of available packages. Think of it like refreshing a webpage before clicking a link."
3. Walk through the commands:
   - `sudo apt update` — update package list
   - `apt search htop` — search for a package
   - `sudo apt install -y htop` — install htop (-y means "yes, do not ask me")
   - `htop` — verify it works (press q to quit)
   - `sudo apt remove htop` — uninstall it
4. Have them install several useful tools:
   - `htop` — interactive process viewer (they will use this in module 04)
   - `tree` — shows directory structure visually
   - `curl` — makes HTTP requests (may already be installed)
   - `net-tools` — gives them `ifconfig` and other network tools
   - `unzip` — for extracting zip files
5. Explain `apt update` vs `apt upgrade`:
   - `apt update` refreshes the list of what is available
   - `apt upgrade` actually installs newer versions of packages you already have
6. Show them `apt list --installed` to see everything installed on the server.

## Prompting coaching
- "install htop on my server" — direct and clear
- "what packages should I install on a new server" — good for learning common tools
- "how do I check what's installed" — practical question

## Quiz questions
- What should you always run before installing a new package?
- What is the difference between `apt update` and `apt upgrade`?
- How do you install a package without being asked for confirmation?
- How do you remove a package you no longer need?

## Hints (only if stuck)
1. If you get "Permission denied," you probably forgot `sudo`.
2. If a package is not found, try `sudo apt update` first to refresh the list.
3. You can install multiple packages at once: `sudo apt install -y htop tree curl`.
