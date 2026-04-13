# Teaching: Deploy App to Remote

## Context
The student has Nginx running on their VM and can see the welcome page in their browser. They have built Node.js apps in Phase 04. Now they will deploy one to the server. This is the full deployment experience: install Node.js, create or copy an app, configure Nginx to proxy to it, and see it live.

## The challenge
Install Node.js on the VM, create a simple Express app, configure Nginx as a reverse proxy, and access the app from the local browser.

## Your approach
1. Frame the task: "Right now Nginx is serving a static HTML page. That is fine for simple websites, but your app needs Node.js. We are going to install Node, run your app, and tell Nginx to forward requests to it."
2. Install Node.js on the server:
   ```
   curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
   sudo apt install -y nodejs
   node --version
   ```
3. Create a simple app on the server (or SCP one from the local machine). Using nano:
   ```
   mkdir -p ~/myapp && cd ~/myapp
   nano server.js
   ```
   Contents:
   ```javascript
   const http = require('http');
   const server = http.createServer((req, res) => {
     res.writeHead(200, { 'Content-Type': 'text/html' });
     res.end('<h1>Hello from my deployed app!</h1><p>Running on the server.</p>');
   });
   server.listen(3000, () => console.log('App running on port 3000'));
   ```
4. Run the app: `node server.js` — it listens on port 3000.
5. Test locally on the server: Open another SSH session or use `curl http://localhost:3000` from the server.
6. Configure Nginx as a reverse proxy. Edit the site config:
   ```
   sudo nano /etc/nginx/sites-available/default
   ```
   Replace the `location /` block with:
   ```
   location / {
       proxy_pass http://localhost:3000;
       proxy_http_version 1.1;
       proxy_set_header Host $host;
       proxy_set_header X-Real-IP $remote_addr;
   }
   ```
7. Test and reload Nginx:
   ```
   sudo nginx -t
   sudo systemctl reload nginx
   ```
8. The payoff: "Now go to `http://vm-ip-address` in your browser." They see their app.
9. Explain what happened: "Your browser sends a request to port 80. Nginx receives it and forwards it to your Node.js app on port 3000. The app responds, and Nginx sends the response back to your browser. This is called a reverse proxy."
10. Point out the problem: "If you press Ctrl+c, your app stops and the website goes down. We need a way to keep it running permanently. That is what systemd is for — the next challenge."

## Prompting coaching
- "install node.js on my server" — clear first step
- "configure nginx as a reverse proxy" — the key configuration
- "my app is not showing up in the browser" — debugging prompt

## Quiz questions
- What does a reverse proxy do?
- Why do we not let users connect directly to port 3000?
- What happens if you stop the Node.js process while Nginx is proxying to it?
- What command reloads the Nginx configuration without stopping it?

## Hints (only if stuck)
1. If the browser shows "502 Bad Gateway," Nginx is running but your Node.js app is not. Make sure `node server.js` is running.
2. If `curl http://localhost:3000` works on the server but the browser does not load, check the Nginx config and firewall.
3. After editing the Nginx config, always run `sudo nginx -t` first, then `sudo systemctl reload nginx`.
