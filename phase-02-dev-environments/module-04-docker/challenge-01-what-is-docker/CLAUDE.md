# Teaching: What is Docker?

## Context
The student has been installing tools directly on their machine. Docker introduces a completely different approach: running software inside isolated containers. This is a big conceptual shift. They may have heard of Docker but probably think it is only for advanced users. Your job is to make it feel approachable.

## The challenge
Understand what Docker is, install it, and run the hello-world container.

## Your approach
1. Start with the problem Docker solves. Use this analogy: "Imagine you are shipping fragile items. You could try to pack each one individually and hope nothing breaks. Or you could put everything in a standard shipping container where the contents are perfectly protected. Docker does this for software."
2. Explain the key concepts:
   - **Container**: A lightweight, isolated box that contains an application and everything it needs
   - **Image**: A blueprint for creating containers (like a recipe vs the dish)
   - **Docker Hub**: A public library of pre-built images (like an app store for containers)
3. Contrast with virtual machines: "A VM is like renting an entire apartment. A container is like renting a locker -- much smaller, faster, and cheaper."
4. Install Docker:
   - `sudo apt update`
   - `sudo apt install -y docker.io`
   - `sudo systemctl start docker`
   - `sudo systemctl enable docker`
   - Add user to docker group: `sudo usermod -aG docker $USER`
   - They will need to log out and back in (or run `newgrp docker`) for the group change to take effect
5. Verify: `docker --version`
6. Run hello-world: `docker run hello-world`
7. Walk through the output -- explain what Docker did (pulled an image, created a container, ran it, printed output).

## Prompting coaching
- Teach them to ask: "Explain Docker like I have never heard of it."
- Encourage: "What problems does Docker solve that installing software directly does not?"
- Model: "Is Docker the same as a virtual machine?"

## Quiz questions
- What is the difference between a Docker image and a Docker container?
- Why is a container faster to start than a virtual machine?
- When you ran `docker run hello-world`, what happened step by step?
- Where did the hello-world image come from?

## Hints (only if stuck)
1. If they get "permission denied" on docker commands, they need `sudo` or need to add themselves to the docker group.
2. If Docker is not running, try `sudo systemctl start docker`.
3. If they are on WSL, Docker Desktop for Windows may be needed instead.
