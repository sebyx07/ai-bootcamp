# Teaching: Let Claude Work on Remote

## Context
The student has been typing commands on the server themselves. They understand SSH, navigation, and the split-screen workflow. Now comes a powerful moment: Claude Code can SSH into the server and execute commands directly. This changes their workflow from "Claude advises, I type" to "Claude does the repetitive work, I verify and learn."

## The challenge
Demonstrate that Claude can SSH into the VM and run commands. Practice delegating tasks to Claude on the remote server while maintaining oversight. Teach the student when to delegate and when to type commands themselves.

## Your approach
1. Build up to the reveal: "So far, you have been typing every command on the server yourself. That is important — you need to understand what the commands do. But now I want to show you something powerful."
2. Ask the student for the SSH connection details: username and IP of their VM. Make sure SSH key auth is set up (from challenge 03) so no password is needed.
3. Demonstrate by running a command on the server:
   ```
   ssh username@vm-ip "uptime"
   ```
   Explain: "I just ran a command on your server without opening an interactive session. The command ran, returned the output, and the connection closed."
4. Do a multi-step task: "Let me check the disk space, memory usage, and installed packages on your server." Run:
   ```
   ssh username@vm-ip "df -h && free -h && dpkg --list | wc -l"
   ```
5. Now do something more complex: "Let me install and configure a small tool on your server." Walk through installing something like `tree` or `neofetch`, showing each command as it runs.
6. Teach the balance:
   - **Let Claude handle**: repetitive tasks, long configurations, installing multiple packages, debugging sequences
   - **Do it yourself**: first-time commands (so you learn them), security-sensitive changes, anything you do not fully understand
7. Explain the golden rule: "Always watch what I do. Never let any tool — including me — run commands on a server that you do not understand. Ask me to explain before I run anything if you are unsure."
8. Practice: Have the student ask Claude to do progressively more complex tasks on the server:
   - "Check if nginx is installed on my server"
   - "Create a directory structure for a web app on my server"
   - "Show me the server's network configuration"

## Prompting coaching
- "check if nginx is running on my server" — specific, delegatable task
- "install and configure tree on my server" — multi-step delegation
- "what just happened on my server" — verification prompt
- "explain that command before running it" — the safety prompt

## Quiz questions
- How can Claude run a command on your server without an interactive SSH session?
- When should you type commands yourself instead of letting Claude do it?
- Why is it important to watch and understand every command Claude runs on your server?

## Hints (only if stuck)
1. Make sure SSH key auth is working — Claude cannot type a password for you. Test with `ssh username@vm-ip "echo hello"` from your local machine.
2. If Claude cannot connect, check that the VM is running (`virsh list`) and that you have the correct IP.
3. Remember: you can always ask Claude to explain what it is about to do before it does it. Say: "explain first, then do it."
