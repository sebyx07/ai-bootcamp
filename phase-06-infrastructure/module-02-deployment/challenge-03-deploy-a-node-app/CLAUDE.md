# Teaching: Deploy a Node App

## Context
The student understands deployment concepts and environment variables. They know Nginx from the previous module. Now they will walk through a real Node.js deployment. If they have a VPS or free tier on a platform like Railway/Render, do it for real. If not, simulate the process locally -- the steps and concepts are the same.

## The challenge
Walk through (or execute) the full deployment of a Node.js app: get it on a server, install dependencies, run it with PM2, and put Nginx in front of it.

## Your approach
1. Review the deployment steps:
   - Get your code to the server (git clone or push)
   - Install Node.js on the server
   - Install dependencies (npm install)
   - Set up environment variables
   - Start the app with PM2 (not `node app.js`)
   - Configure Nginx as a reverse proxy
2. Explain PM2: "If your app crashes, PM2 restarts it. If the server reboots, PM2 starts your app automatically. It is a process manager."
3. If deploying for real (VPS):
   - SSH into the server
   - Clone the repo
   - Run through each step above
4. If simulating locally:
   - Install PM2 globally: `npm install -g pm2`
   - Start the app: `pm2 start app.js --name myapp`
   - Show PM2 commands: `pm2 list`, `pm2 logs`, `pm2 restart myapp`, `pm2 stop myapp`
   - Configure Nginx reverse proxy (from the previous module)
5. Show the full request flow: Browser -> Nginx (port 80) -> Node app (port 3000) -> Response back.
6. Discuss what could go wrong: app crashes, port conflicts, missing env vars, wrong Node version.

## Prompting coaching
"Deploy my node app with pm2" is a great prompt. If something goes wrong, "check pm2 logs" or "why is my app crashing" are good debugging prompts.

## Quiz questions
- Why use PM2 instead of running `node app.js` directly?
- What command shows you the logs from a PM2-managed app?
- What is the full journey of an HTTP request from a user's browser to your Node app and back?

## Hints (only if stuck)
1. Install PM2: `npm install -g pm2`. Start your app: `pm2 start app.js`.
2. Check if your app is running: `pm2 list`. Check logs: `pm2 logs`.
3. Make sure your Nginx `proxy_pass` points to the right port (the one your app listens on).
