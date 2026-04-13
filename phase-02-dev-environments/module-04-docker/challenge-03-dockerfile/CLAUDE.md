# Teaching: Dockerfile

## Context
The student can run existing Docker images. Now they need to create their own. A Dockerfile is like a recipe -- it tells Docker how to build an image step by step. This is where Docker goes from "cool toy" to "essential tool."

## The challenge
Write a Dockerfile that packages a simple application, build it into an image, and run it.

## Your approach
1. Create a project directory:
   ```
   mkdir ~/docker-challenge && cd ~/docker-challenge
   ```
2. First, create a simple application to containerize. Use Node.js since they already have it:
   ```javascript
   // app.js
   const http = require('http');
   const server = http.createServer((req, res) => {
     res.writeHead(200, {'Content-Type': 'text/plain'});
     res.end('Hello from inside a Docker container!\n');
   });
   server.listen(3000, () => console.log('Server running on port 3000'));
   ```
3. Now create the Dockerfile line by line, explaining each one:
   ```dockerfile
   FROM node:20-alpine
   WORKDIR /app
   COPY app.js .
   EXPOSE 3000
   CMD ["node", "app.js"]
   ```
   - `FROM` — the base image (like choosing your starting ingredients)
   - `WORKDIR` — sets the working directory inside the container
   - `COPY` — copies files from your machine into the container
   - `EXPOSE` — documents which port the app uses
   - `CMD` — the command that runs when the container starts
4. Build the image: `docker build -t my-app .`
   - Explain the `-t` flag (tag/name) and the `.` (build context)
5. Run it: `docker run -d -p 3000:3000 --name my-app my-app`
6. Test it: `curl localhost:3000`
7. Clean up: `docker stop my-app && docker rm my-app`

## Prompting coaching
- Teach: "What does each line of this Dockerfile do?"
- Encourage: "How would I change this to use Python instead of Node?"
- Model: "What is the difference between CMD and RUN in a Dockerfile?"

## Quiz questions
- What does `FROM node:20-alpine` mean? What is "alpine"?
- What is the difference between `RUN` and `CMD`?
- Why do we use `COPY` instead of just accessing our files directly?
- What does `docker build -t my-app .` do? What is the `.`?

## Hints (only if stuck)
1. The Dockerfile must be named exactly `Dockerfile` (capital D, no extension).
2. If the build fails, check that `app.js` is in the same directory as the Dockerfile.
3. If port 3000 is busy, use a different host port: `docker run -d -p 4000:3000 my-app`.
