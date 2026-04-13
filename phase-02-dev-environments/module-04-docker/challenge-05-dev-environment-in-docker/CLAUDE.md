# Teaching: Dev Environment in Docker

## Context
The student knows Docker basics, Dockerfiles, and Docker Compose. Now they will learn the most practical application: using Docker as their development environment. This means they can code on their machine while the app runs inside a container, with changes reflected in real time.

## The challenge
Set up a Docker-based development environment for a Node.js application where file changes on the host are immediately visible inside the container.

## Your approach
1. Explain the value: "Instead of installing Node, PostgreSQL, Redis, and everything else on your machine, you define it all in Docker. Anyone who clones your project can run it with one command."
2. Create a project:
   ```
   mkdir ~/docker-dev && cd ~/docker-dev
   ```
3. Create a simple Node.js app (`app.js`):
   ```javascript
   const http = require('http');
   const server = http.createServer((req, res) => {
     res.writeHead(200, {'Content-Type': 'text/html'});
     res.end('<h1>Edit me! I will update automatically.</h1>\n');
   });
   server.listen(3000, '0.0.0.0', () => {
     console.log('Server running at http://localhost:3000');
   });
   ```
4. Create a `package.json`:
   ```json
   {
     "name": "docker-dev-demo",
     "scripts": {
       "start": "node app.js",
       "dev": "node --watch app.js"
     }
   }
   ```
5. Create a `Dockerfile`:
   ```dockerfile
   FROM node:20-alpine
   WORKDIR /app
   COPY package.json .
   CMD ["npm", "run", "dev"]
   ```
6. Create `docker-compose.yml`:
   ```yaml
   services:
     app:
       build: .
       ports:
         - "3000:3000"
       volumes:
         - .:/app
       environment:
         - NODE_ENV=development
   ```
7. Key teaching moment -- explain the volume mount: `- .:/app` maps the current directory to /app in the container. This means editing files locally changes them inside the container instantly.
8. Run it: `docker compose up`
9. Have them edit `app.js` locally, change the message, and see it update (with `--watch` flag Node will restart).
10. Show them `docker compose exec app sh` to get a shell inside the running container.

## Prompting coaching
- Teach: "How do I set up Docker so I can develop without installing anything?"
- Encourage: "What would I need to add to support a database too?"
- Model: "What is the difference between running my app locally vs. in Docker?"

## Quiz questions
- What does the volume mount `.:/app` do?
- Why do we use `node --watch` in the dev script?
- What are the pros and cons of developing inside Docker vs. locally?
- How would you add a PostgreSQL database to this setup?

## Hints (only if stuck)
1. If file changes are not detected, make sure the volume mount is correct in docker-compose.yml.
2. `docker compose up --build` forces a rebuild if the Dockerfile changed.
3. Use `docker compose exec app sh` to get inside the container and debug.
