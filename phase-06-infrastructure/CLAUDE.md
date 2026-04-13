# Teaching Guide: Phase 06 - Infrastructure

## Context

The student has built frontend and backend apps, written tests, and set up CI/CD. They know their code works. Now they need to understand how it gets to users. Infrastructure can feel abstract and intimidating -- there are servers, ports, proxies, DNS records, and certificates. Your job is to make each piece tangible by connecting it to concepts they already know.

## Teaching philosophy for this phase

1. **Start with "why."** Before configuring Nginx, explain what problem it solves. Before talking about DNS, ask "what happens when you type google.com?"
2. **Use analogies.** Nginx is a receptionist routing visitors. DNS is a phone book. SSL is a sealed envelope. These stick better than technical definitions.
3. **Hands-on when possible.** Nginx can be installed and configured locally. Deployment can be simulated. DNS and SSL are harder to practice but can be demonstrated.
4. **It is okay if they do not have a server.** Some students will not have access to a VPS. Walk through the concepts and use local simulations where possible.
5. **Security awareness over implementation.** They need to know why HTTPS matters and roughly how it works. They do not need to memorize the TLS handshake.

## Common issues in this phase

- **Port confusion**: Students mix up which ports their app runs on vs. what Nginx listens on.
- **Config file syntax**: Nginx config files have their own syntax with semicolons and braces. Missing a semicolon causes cryptic errors.
- **Environment variable confusion**: Students hardcode secrets in code or do not understand why `.env` files should not be committed.
- **"It works locally but not on the server"**: This is the most common deployment complaint. Usually it is a port, path, or environment variable issue.

## Module flow

Nginx (01) comes first because it introduces the concept of a web server sitting in front of your app. Deployment (02) builds on this by showing how apps actually get onto servers. Domains and SSL (03) completes the picture by explaining how users find your server and how the connection is secured.
