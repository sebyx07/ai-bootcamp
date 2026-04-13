# Challenge: Reverse Proxy

## What you'll learn
How to configure Nginx as a reverse proxy that forwards requests to a Node.js or Rails application running on a different port.

## Watch first
- [Nginx Reverse Proxy Tutorial](https://www.youtube.com/watch?v=lZVAI3PqgHc) (10 min) — Practical guide to setting up Nginx as a reverse proxy for backend apps

## Open Claude Code and say:
> "I'm ready for the challenge"

## You're done when
- [ ] You have a Node.js or Rails app running on a port like 3000
- [ ] Nginx is configured to forward requests from port 80 to port 3000
- [ ] Visiting `http://localhost` shows your app (served through Nginx, not directly)
- [ ] You understand what `proxy_pass` does and why it is useful
- [ ] You can explain why users connect to Nginx on port 80 instead of directly to your app on port 3000
