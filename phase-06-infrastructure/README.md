# Phase 06: Infrastructure

## What this phase is about

You have built apps. Now you need to put them on the internet so other people can use them. Infrastructure is everything that sits between your code and your users: web servers, hosting platforms, domain names, and security certificates. This phase teaches you how software goes from "works on my machine" to "works for everyone."

By the end of this phase, you will understand how Nginx serves web traffic, how applications get deployed to servers, how domain names work, and how HTTPS keeps connections secure.

## Modules

| Module | What you will learn |
|--------|-------------------|
| **01 - Nginx** | What Nginx is, how to serve static files, and how to use it as a reverse proxy |
| **02 - Deployment** | What deployment means, environment variables, and how to deploy Node.js and Rails apps |
| **03 - Domains and SSL** | How DNS turns names into addresses and how HTTPS encrypts web traffic |

## Prerequisites

- Completed Phase 04 (you should have built Node.js and Rails applications)
- Completed Phase 05 (your apps should have tests)
- Familiarity with the terminal and basic Linux commands

## How long will this take?

Expect 6-8 hours. Module 01 (Nginx) is the most hands-on. Module 02 (Deployment) walks through the process even if you do not have a live server. Module 03 (Domains and SSL) is mostly conceptual awareness.

## Tips for this phase

- **You do not need a server to learn this.** Many of the exercises work locally or use free tools.
- **Infrastructure problems are usually configuration problems.** A misplaced line in a config file can break everything. Read carefully.
- **Understanding beats memorization.** You will not remember every Nginx directive. You will remember what Nginx does and how to look up the rest.
- **Security is not optional.** HTTPS exists for a reason. Never deploy without it.
