# Teaching: Follow Logs Remotely

## Context
The student has the split-screen workflow set up: Claude on the left, server on the right. Now they need to learn one of the most powerful debugging techniques: watching logs in real time. When something breaks on a server, the first thing you do is check the logs. Watching them live while making changes is how professionals debug server issues.

## The challenge
Set up a three-pane tmux layout: Claude on the left, server commands in the top-right, live logs in the bottom-right. Practice watching logs update in real time.

## Your approach
1. Explain why logs matter: "Every time something happens on your server — a service starts, a request comes in, an error occurs — it gets written to a log file. Watching logs in real time is like watching a security camera for your server."
2. Set up a three-pane layout:
   - Left pane: Claude Code
   - Right pane: SSH to the server
   - Split the right pane horizontally (`Ctrl+b "` while in the right pane): top for commands, bottom for logs
3. In the log pane (bottom-right), run: `sudo tail -f /var/log/syslog`
4. Explain `tail -f`:
   - `tail` shows the last lines of a file
   - `-f` means "follow" — it keeps watching and shows new lines as they appear
   - `Ctrl+c` stops following
5. In the command pane (top-right), do things that generate log entries:
   - `sudo systemctl restart ssh` — watch the log pane update
   - `logger "hello from the terminal"` — writes a custom message to syslog
6. Show them the main log locations:
   - `/var/log/syslog` — general system messages
   - `/var/log/auth.log` — login attempts and authentication
   - `/var/log/kern.log` — kernel messages
7. Introduce `journalctl -f` as the modern alternative: "journalctl is the newer way to read logs on systems using systemd. `journalctl -f` is like `tail -f` but for all system logs."

## Prompting coaching
- "how do I watch logs in real time" — leads to tail -f
- "where are the log files on ubuntu" — good for learning the filesystem
- "what does this log message mean" — the key debugging prompt

## Quiz questions
- What does the `-f` flag do in `tail -f`?
- What command writes a custom message to the system log?
- Name two important log files on an Ubuntu server.
- What is the modern alternative to `tail -f /var/log/syslog`?

## Hints (only if stuck)
1. If `/var/log/syslog` does not exist, try `journalctl -f` instead — some minimal installs use only journald.
2. Press `Ctrl+c` to stop following a log file.
3. To see the last 50 lines of a log: `tail -n 50 /var/log/syslog`.
