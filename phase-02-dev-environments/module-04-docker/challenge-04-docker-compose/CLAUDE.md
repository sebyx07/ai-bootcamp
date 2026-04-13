# Teaching: Docker Compose

## Context
The student can build and run individual containers. In reality, applications need multiple services (web server, database, cache). Running each one manually with `docker run` is tedious and error-prone. Docker Compose solves this by defining everything in one file.

## The challenge
Create a docker-compose.yml file that runs a web application with a database, and manage it with Docker Compose commands.

## Your approach
1. Explain the problem: "Imagine your app needs a web server AND a database. You would need two `docker run` commands with correct ports, networks, and names. Docker Compose lets you define all of that in one file."
2. Create a project directory:
   ```
   mkdir ~/compose-challenge && cd ~/compose-challenge
   ```
3. Create a `docker-compose.yml` file:
   ```yaml
   services:
     web:
       image: nginx:alpine
       ports:
         - "8080:80"
       volumes:
         - ./html:/usr/share/nginx/html

     db:
       image: postgres:16-alpine
       environment:
         POSTGRES_PASSWORD: mysecretpassword
         POSTGRES_DB: myapp
       ports:
         - "5432:5432"
   ```
4. Create the HTML directory and a simple page:
   ```
   mkdir html
   echo "<h1>Hello from Docker Compose!</h1>" > html/index.html
   ```
5. Explain each section of the compose file:
   - `services` — defines each container
   - `image` — which Docker image to use
   - `ports` — port mapping (host:container)
   - `volumes` — share files between host and container
   - `environment` — set environment variables
6. Run it: `docker compose up -d`
7. Verify both services:
   - `curl localhost:8080` — should show the HTML page
   - `docker compose ps` — shows both containers running
8. Show logs: `docker compose logs`
9. Tear it down: `docker compose down`

## Prompting coaching
- Teach: "How do I run multiple containers that work together?"
- Encourage: "What would I add if I also wanted a Redis cache?"
- Model: "What is the difference between `docker compose up` and `docker compose start`?"

## Quiz questions
- What is the difference between `docker compose up` and `docker compose up -d`?
- What does `docker compose down` do that `docker compose stop` does not?
- What does the `volumes` section do?
- How do the containers communicate with each other?

## Hints (only if stuck)
1. YAML is whitespace-sensitive. Use spaces, not tabs. Indentation matters.
2. If port 5432 is already in use, change it to `5433:5432`.
3. Use `docker compose logs <service>` to see logs for a specific service.
