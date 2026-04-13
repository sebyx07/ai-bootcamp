# Challenge: Reading Logs

## What you'll learn
How to use journalctl and log files to find out what happened on your server and debug problems.

## Watch first
- [Linux Crash Course - journalctl](https://www.youtube.com/watch?v=r2GVTMtO3Xw) (12 min) — Learn Linux TV covers journalctl for reading and filtering systemd logs
- [Linux Log Files Explained](https://www.youtube.com/watch?v=6TEvEimVJzM) (10 min) — Where Linux keeps its log files and how to read them

## Open Claude Code and say:
> "I'm ready for the challenge"

## You're done when
- [ ] You can view logs for a specific service with `journalctl -u service-name`
- [ ] You can follow logs in real time with `journalctl -f`
- [ ] You can filter logs by time with `--since` and `--until`
- [ ] You can view only error messages with `-p err`
- [ ] You can read Nginx access and error logs in `/var/log/nginx/`
- [ ] You have used logs to find and understand an error
