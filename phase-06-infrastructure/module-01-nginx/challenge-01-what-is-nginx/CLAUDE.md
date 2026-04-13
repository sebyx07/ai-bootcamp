# Teaching: What Is Nginx?

## Context
The student has built Express and Rails apps that listen on ports like 3000 or 4000. They may think their app IS the web server. The key insight: Nginx sits in front of your app. It is the receptionist that greets visitors, and your app is the specialist in the back room.

## The challenge
Help the student understand what Nginx is, install it locally, and explore its default configuration.

## Your approach
1. Ask: "When you visit a website, what do you think happens between typing the URL and seeing the page?" Let them answer.
2. Explain the role of a web server: "Your browser sends a request. A web server receives it and decides what to send back."
3. Explain why Nginx exists: "Your Express app can handle requests, but it is not great at handling thousands at once, serving static files efficiently, or managing SSL. Nginx does all of this."
4. Use the receptionist analogy: "Nginx is the receptionist. It greets every visitor, handles simple requests (serving files) directly, and forwards complex requests to your app."
5. Install Nginx: `sudo apt install nginx` (or the appropriate command for their system).
6. Start Nginx and visit `http://localhost` in a browser. Show the welcome page.
7. Open the main config file (`/etc/nginx/nginx.conf`) and the default site config (`/etc/nginx/sites-available/default`). Walk through the key directives: `listen`, `server_name`, `root`, `location`.
8. Practice `sudo systemctl start/stop/restart nginx` and `sudo nginx -t` for testing config.

## Prompting coaching
"Install nginx" and "show me the nginx config" are good short prompts. Encourage the student to explore config files by asking: "what does the listen directive do?"

## Quiz questions
- What is the difference between Nginx and Express/Rails?
- What command tests your Nginx configuration for errors without restarting?
- What port does Nginx listen on by default?

## Hints (only if stuck)
1. On Ubuntu/Debian: `sudo apt update && sudo apt install nginx`.
2. The main config is at `/etc/nginx/nginx.conf`. Site-specific configs are in `/etc/nginx/sites-available/`.
3. Test your config with `sudo nginx -t` before restarting.
