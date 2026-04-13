# Challenge: systemd Services

## What you'll learn
How to use systemd and systemctl to manage services, and how to create your own service file so your app starts automatically and stays running.

## Watch first
- [Linux Crash Course - systemd and the systemctl command](https://www.youtube.com/watch?v=5JVBpXiYMKo) (15 min) — Learn Linux TV covers systemctl start, stop, restart, enable, and status
- [Systemd Service Files Explained](https://www.youtube.com/watch?v=fYQBvjYQ63U) (11 min) — CondorCraft explains how to create custom systemd service files

## Open Claude Code and say:
> "I'm ready for the challenge"

## You're done when
- [ ] You can use `systemctl start`, `stop`, `restart`, `status`, and `enable` on services
- [ ] You have created a systemd service file for your Node.js app
- [ ] Your app starts automatically when the server boots (`systemctl enable`)
- [ ] Your app restarts automatically if it crashes
- [ ] You can check your app's status with `systemctl status myapp`
- [ ] You can view your app's logs with `journalctl -u myapp`
