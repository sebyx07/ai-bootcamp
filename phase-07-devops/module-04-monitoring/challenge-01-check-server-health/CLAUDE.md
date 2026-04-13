# Teaching: Check Server Health

## Context
The student has a fully set up server: users, firewall, Nginx, their app running as a systemd service. Now they need to learn the routine that every sysadmin and developer does when they log into a server: a quick health check. These commands take 30 seconds and tell you if the server is healthy or needs attention.

## The challenge
Build a "health check routine" — a short list of commands to run every time you SSH into a server to quickly assess its state.

## Your approach
1. Frame it: "Imagine you get a message at 2 AM: 'The website is down.' You SSH into the server. What do you check first? This challenge teaches you that muscle-memory routine."
2. The health check routine (teach each command):
   - `uptime` — how long has the server been running? If it just rebooted, something might have gone wrong. Also shows load averages.
   - `w` — who is logged in right now? Shows active SSH sessions.
   - `systemctl status nginx` — is the web server running?
   - `systemctl status myapp` — is your app running?
   - `df -h` — is the disk full? (covered more in next challenge)
   - `free -h` — is the server out of memory? (covered more in next challenge)
3. Explain load averages from `uptime`: "The three numbers (e.g., 0.12, 0.08, 0.05) are the average number of processes waiting to run over the last 1, 5, and 15 minutes. On a 2-CPU machine, anything under 2.0 is fine. Over that means the server is overloaded."
4. Have them practice the routine:
   - SSH into the server
   - Run all six commands
   - Report back what they found
5. Make it a habit: "Every time you SSH into a server, run `uptime` first. It becomes second nature."
6. Show a one-liner for quick checks:
   ```
   uptime && systemctl is-active nginx && systemctl is-active myapp
   ```
7. Explain the mindset: "Monitoring is not about memorizing commands. It is about asking: Is the server up? Are the services running? Does it have enough resources? Are there errors?"

## Prompting coaching
- "is my server healthy" — good starting prompt
- "check if nginx is running" — specific and quick
- "what does uptime mean" — good for understanding output
- "my server seems slow" — debugging prompt

## Quiz questions
- What does the `uptime` command tell you?
- What do load averages represent?
- What is the fastest way to check if a service is running?
- Name three things to check when you first log into a server.

## Hints (only if stuck)
1. `systemctl is-active nginx` returns just "active" or "inactive" — perfect for quick checks.
2. Load averages depend on CPU count. Run `nproc` to see how many CPUs your server has.
3. If a service is not running, check its logs with `journalctl -u service-name -n 20`.
