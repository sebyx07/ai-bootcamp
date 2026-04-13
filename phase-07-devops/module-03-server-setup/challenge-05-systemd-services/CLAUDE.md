# Teaching: systemd Services

## Context
The student has a Node.js app running on the server behind Nginx. The problem: if they close the terminal or the server reboots, the app stops. systemd solves this. It is the service manager built into Linux that starts services at boot, restarts them if they crash, and provides logging. This is how every serious application runs on a Linux server.

## The challenge
Learn the essential systemctl commands, then create a systemd service file for the Node.js app so it runs as a managed, auto-starting, auto-restarting service.

## Your approach
1. Explain the problem: "Right now your app only runs when you manually start it with `node server.js`. If you close the terminal, it stops. If the server reboots, it does not come back. In production, apps need to run forever without babysitting. That is what systemd does."
2. First, teach systemctl with an existing service (nginx):
   - `sudo systemctl status nginx` — see if it is running, when it started, recent logs
   - `sudo systemctl stop nginx` — stop it
   - `sudo systemctl start nginx` — start it
   - `sudo systemctl restart nginx` — stop then start
   - `sudo systemctl enable nginx` — start automatically at boot
   - `sudo systemctl disable nginx` — do not start at boot
   - `sudo systemctl is-enabled nginx` — check if it starts at boot
3. Now create a service file for the Node.js app:
   ```
   sudo nano /etc/systemd/system/myapp.service
   ```
   Contents:
   ```ini
   [Unit]
   Description=My Node.js Application
   After=network.target

   [Service]
   Type=simple
   User=deploy
   WorkingDirectory=/home/deploy/myapp
   ExecStart=/usr/bin/node server.js
   Restart=on-failure
   RestartSec=5
   Environment=NODE_ENV=production
   Environment=PORT=3000

   [Install]
   WantedBy=multi-user.target
   ```
4. Explain each section:
   - `[Unit]` — what this service is and when to start it (after networking is ready)
   - `[Service]` — how to run it: which user, which directory, what command, what to do if it crashes
   - `[Install]` — when this service should be started (multi-user.target = normal boot)
   - `Restart=on-failure` — if the app crashes, systemd restarts it
   - `RestartSec=5` — wait 5 seconds before restarting
5. Make sure the app files are in the right place. If they were in the original user's home, copy them:
   ```
   sudo cp -r ~/myapp /home/deploy/myapp
   sudo chown -R deploy:deploy /home/deploy/myapp
   ```
6. Activate the service:
   ```
   sudo systemctl daemon-reload
   sudo systemctl start myapp
   sudo systemctl status myapp
   sudo systemctl enable myapp
   ```
7. Test the crash recovery: `sudo systemctl stop myapp`, then `systemctl status myapp`. Start it again. Or kill the process: `sudo kill $(pgrep -f "node server.js")` — watch it restart automatically.
8. Show the logs: `journalctl -u myapp -f` — this shows the app's output in real time, just like watching `console.log` statements.

## Prompting coaching
- "create a systemd service for my node app" — the key task
- "check if my app is running" — leads to systemctl status
- "my app crashed, why" — leads to journalctl
- "make my app start on boot" — leads to systemctl enable

## Quiz questions
- What is the difference between `systemctl start` and `systemctl enable`?
- What does `Restart=on-failure` do in a service file?
- Where do custom service files go on the filesystem?
- How do you view logs for a specific service?
- After editing a service file, what command must you run before restarting the service?

## Hints (only if stuck)
1. After editing a `.service` file, always run `sudo systemctl daemon-reload` before starting or restarting the service.
2. If the service fails to start, check the logs: `journalctl -u myapp -n 50` shows the last 50 log lines.
3. Make sure the `ExecStart` path points to the actual node binary. Find it with `which node`.
