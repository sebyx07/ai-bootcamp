# Teaching: Navigate a Remote Server

## Context
The student can SSH into their VM. They know basic terminal commands (cd, ls, cat, grep, nano) from their local machine. Now they need to apply those same skills on the remote server and learn the Linux filesystem layout — where configuration files live, where logs are, where applications get installed.

## The challenge
SSH into the VM and explore the filesystem. Learn the standard Linux directory structure and practice finding and reading files.

## Your approach
1. Have them SSH into the VM first.
2. Start at the root: `ls /` and explain the key directories:
   - `/etc` — configuration files ("etcetera" or "editable text configuration"). This is where you configure almost everything.
   - `/var/log` — log files. When something goes wrong, you look here.
   - `/home` — user home directories. Their stuff lives here.
   - `/tmp` — temporary files. Gets cleaned up automatically.
   - `/usr` — user programs and utilities. Most installed software ends up here.
   - `/opt` — optional software, usually third-party applications.
3. Practice navigation exercises:
   - "Go to /etc and find a file called hostname. Read it."
   - "Go to /var/log and see what log files exist."
   - "Use grep to search for your username in /etc/passwd."
   - "Use find to locate all .conf files in /etc."
4. Practice editing with nano: Have them create or edit a file. Remind them: "On a remote server, you will not have VS Code. nano is your editor here. It works everywhere."
5. Show them `less` for reading long files: `less /var/log/syslog`. Teach `/` to search inside less, `q` to quit.
6. Emphasize: "Everything you already know works here. cd, ls, cat, grep, nano — same commands, different computer."

## Prompting coaching
- "where are config files on linux" — good question for learning filesystem layout
- "find all log files on the server" — practical and focused
- "how do I edit a file on the server" — leads to nano

## Quiz questions
- What directory contains configuration files on a Linux server?
- Where do log files typically live?
- What is the difference between `cat` and `less` when reading a file?
- If you need to edit a configuration file on a remote server, what editor would you use?

## Hints (only if stuck)
1. Remember you can always check where you are with `pwd` and what is around you with `ls -la`.
2. To read a long file page by page, use `less filename` instead of `cat filename`.
3. To search for a file by name: `find /etc -name "*.conf"` finds all .conf files under /etc.
