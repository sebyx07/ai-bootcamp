# Teaching: What Is Deployment?

## Context
The student has only run apps locally (localhost). They understand Nginx from the previous module. Now they need to understand the bigger picture: how code goes from their laptop to a server that anyone on the internet can access. This is conceptual -- they may not have a server to deploy to, and that is fine.

## The challenge
Walk the student through the deployment process conceptually, covering what changes between development and production, what infrastructure is needed, and what platforms are available.

## Your approach
1. Ask: "Right now your app runs on localhost. What would need to change for anyone in the world to use it?"
2. Walk through the journey:
   - Your code needs to be on a server (not your laptop)
   - That server needs to be always on and connected to the internet
   - The server needs the right software (Node.js, Ruby, Nginx, database)
   - Your app needs to be configured for production (different database, secrets, etc.)
   - A domain name points to the server's IP address
3. Explain development vs production:
   - Development: localhost, debug mode, fake data, no security needed
   - Production: real server, optimized, real data, HTTPS required
4. Introduce hosting options:
   - VPS (DigitalOcean, Linode): you manage everything
   - PaaS (Railway, Render, Heroku): they manage the server, you just push code
   - Containers (Docker + cloud): portable, reproducible deployments
5. Walk through a typical deployment checklist: push code, install dependencies, run migrations, start the app, configure the web server, set up SSL.

## Prompting coaching
Encourage the student to ask questions about things they do not understand: "what is a VPS?" is a great prompt. Short and specific.

## Quiz questions
- What is the difference between development and production?
- Why can't you just leave your laptop on and let people connect to it?
- What is the advantage of a PaaS like Railway over a VPS like DigitalOcean?

## Hints (only if stuck)
1. Think of deployment as moving your app from your laptop to a computer that is always on.
2. The big differences in production: real database, no debug mode, HTTPS, a domain name.
3. A VPS gives you full control but more work. A PaaS gives you less control but handles the hard parts.
