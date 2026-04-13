# Teaching: Reading Logs

## Context
The student has learned the health check routine and resource monitoring. Now they need the final monitoring skill: reading logs. When something goes wrong, logs tell you what happened. journalctl is the modern way to read logs on systemd-based systems, and traditional log files in /var/log are still important to know.

## The challenge
Learn to use journalctl to read, filter, and follow logs. Also learn to read Nginx and application logs from /var/log. Practice finding errors in logs.

## Your approach
1. Explain why logs matter: "Logs are the server's diary. Every service writes what it is doing, including errors. When something breaks, logs are where you find out why."

2. Start with journalctl basics:
   - `journalctl` — show all logs (press q to quit, arrows to scroll)
   - `journalctl -u nginx` — show only nginx logs
   - `journalctl -u myapp` — show only your app's logs
   - `journalctl -u myapp -f` — follow your app's logs in real time (like tail -f)
   - `journalctl -u myapp -n 50` — show the last 50 lines

3. Teach filtering:
   - By time: `journalctl --since "1 hour ago"`
   - By date: `journalctl --since "2024-01-15 10:00" --until "2024-01-15 12:00"`
   - By today: `journalctl --since today`
   - By priority: `journalctl -p err` — only errors and worse
   - By boot: `journalctl -b` — logs since last boot

4. Show traditional log files:
   - `ls /var/log/` — see what is there
   - `sudo tail -20 /var/log/nginx/access.log` — recent web requests
   - `sudo tail -20 /var/log/nginx/error.log` — recent Nginx errors
   - `sudo tail -f /var/log/nginx/access.log` — follow access log live
   - `sudo cat /var/log/auth.log | grep "Failed"` — find failed login attempts

5. Practice a real debugging scenario:
   - Stop the Node.js app: `sudo systemctl stop myapp`
   - Visit the website in the browser — it will show an error
   - Check the Nginx error log: `sudo tail /var/log/nginx/error.log`
   - Check the app status: `systemctl status myapp`
   - Check the app logs: `journalctl -u myapp -n 20`
   - Fix it: `sudo systemctl start myapp`
   - This teaches the debugging loop: notice problem, check logs, find cause, fix it.

6. Teach the power combo: "In one tmux pane, run `journalctl -u myapp -f`. In another pane, make requests to the app. Watch the logs update in real time. This is how you debug in production."

7. Briefly mention log rotation: "Log files can get huge. Linux automatically rotates them (compresses and archives old ones) using logrotate. You do not need to configure this now, just know it exists."

## Prompting coaching
- "show me the app logs" — quick debugging start
- "find errors in the nginx log" — specific and useful
- "what happened on my server in the last hour" — time-filtered investigation
- "my app crashed, help me find why" — the ultimate debugging prompt

## Quiz questions
- What command shows logs for a specific systemd service?
- How do you follow logs in real time with journalctl?
- What does `-p err` filter for?
- Where are the Nginx access and error logs?
- What is the first thing you should check when your app stops working?

## Hints (only if stuck)
1. If journalctl shows too much output, use `-n 50` to see only the last 50 lines, or `--since "10 minutes ago"` to narrow by time.
2. Nginx logs are in `/var/log/nginx/`. The two files you care about are `access.log` and `error.log`.
3. The debugging loop is: check status (`systemctl status`), check logs (`journalctl -u`), find the error, fix it, restart the service.
