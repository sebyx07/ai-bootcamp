# Teaching: Install Nginx on Remote

## Context
The student learned about Nginx in Phase 06 on their local machine. Now they are installing it on their remote VM — a real server setup. The firewall is already configured to allow HTTP traffic on port 80. This time it is more real: they are SSHing in, installing, and then accessing it from their local browser.

## The challenge
SSH into the VM, install Nginx, verify it is running, and access the welcome page from the local machine's browser.

## Your approach
1. Remind them of what Nginx is: "You learned about Nginx in Phase 06. Now you are installing it on a real server. Nginx will sit in front of your app and handle incoming web requests."
2. SSH into the VM and install Nginx:
   ```
   sudo apt update
   sudo apt install -y nginx
   ```
3. Verify it is running: `sudo systemctl status nginx` — should show "active (running)".
4. The exciting moment: "Now open your local browser and go to `http://vm-ip-address`. You should see the Nginx welcome page." This is a milestone — they are serving a web page from their server.
5. Explore the configuration:
   - Main config: `cat /etc/nginx/nginx.conf`
   - Site config: `cat /etc/nginx/sites-available/default`
   - Explain: `listen 80` means Nginx listens on port 80, `root /var/www/html` is where it serves files from.
6. Practice essential commands:
   - `sudo systemctl stop nginx` — stop it (the welcome page disappears)
   - `sudo systemctl start nginx` — start it (the welcome page is back)
   - `sudo systemctl restart nginx` — restart it (use after config changes)
   - `sudo nginx -t` — test config for errors without restarting
7. Create a custom page:
   ```
   echo "<h1>Hello from my server!</h1>" | sudo tee /var/www/html/index.html
   ```
   Refresh the browser — they see their custom page.
8. Point out: "This is the same workflow you will use when deploying a real app. Install Nginx, configure it, and serve content."

## Prompting coaching
- "install nginx on my server" — clear and direct
- "where is the nginx config file" — good for exploring
- "test my nginx configuration" — important habit to build

## Quiz questions
- What command tests your Nginx config for errors?
- Where does Nginx serve files from by default?
- What port does Nginx listen on by default?
- What is the difference between `systemctl restart nginx` and `systemctl reload nginx`?

## Hints (only if stuck)
1. If you cannot reach the Nginx welcome page, check: is Nginx running? (`systemctl status nginx`), is the firewall allowing port 80? (`sudo ufw status`), do you have the right IP? (`ip addr` on the VM).
2. If `nginx -t` shows an error, read the error message carefully — it usually tells you the exact file and line number.
3. If you changed the config, always run `sudo nginx -t` before restarting.
