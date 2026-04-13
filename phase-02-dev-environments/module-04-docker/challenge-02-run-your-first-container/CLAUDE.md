# Teaching: Run Your First Container

## Context
The student has Docker installed and has run hello-world. Now they need to learn the essential Docker commands by running real containers they can interact with. This challenge builds muscle memory with the most common Docker operations.

## The challenge
Pull images, run interactive containers, and manage container lifecycle (start, stop, remove).

## Your approach
1. Start with pulling an image: `docker pull ubuntu`
   - Explain what is happening: "You are downloading a minimal Ubuntu Linux system. The whole thing. In seconds."
2. Run it interactively: `docker run -it ubuntu bash`
   - Explain the flags: `-i` = interactive, `-t` = terminal
   - They are now INSIDE a container. Have them explore:
     - `cat /etc/os-release` — see it is Ubuntu
     - `ls /` — familiar Linux file system
     - `whoami` — they are root
     - `exit` — leave the container
3. Teach container management:
   - `docker ps` — shows running containers (probably empty now)
   - `docker ps -a` — shows ALL containers including stopped ones
   - Run a background container: `docker run -d --name my-nginx -p 8080:80 nginx`
   - `docker ps` — now shows the running nginx container
   - Open a browser or `curl localhost:8080` — they should see the nginx welcome page
   - `docker stop my-nginx`
   - `docker rm my-nginx`
4. Teach the naming pattern: `docker run --name <name>` gives containers memorable names.
5. Show `docker images` to list downloaded images.

## Prompting coaching
- Teach: "What flags do I need to run a container I can interact with?"
- Encourage: "How do I see what containers are running right now?"
- Model: "What is the difference between stopping and removing a container?"

## Quiz questions
- What does `-it` mean in `docker run -it ubuntu bash`?
- What is the difference between `docker ps` and `docker ps -a`?
- What does `-p 8080:80` do?
- When you exit an interactive container, is it deleted?

## Hints (only if stuck)
1. If port 8080 is busy, try a different port: `docker run -d -p 9090:80 nginx`.
2. To remove all stopped containers at once: `docker container prune`.
3. If they cannot curl localhost, make sure the container is still running with `docker ps`.
