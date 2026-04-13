# Phase 07: DevOps — Remote Servers and Deployment

## What this phase is about

You have built apps that run on your own machine. Now you will learn to run them on a separate server — the way real software gets delivered to users. DevOps is the practice of setting up, deploying to, and maintaining servers so your applications stay running reliably.

In this phase you will create a virtual machine on your own computer that acts like a remote server. You will SSH into it, set it up from scratch, deploy an application, and learn to monitor its health. Most importantly, you will learn the split-screen workflow that professional developers use every day: Claude Code on one side, your server on the other.

By the end of this phase, you will be comfortable working on a remote Linux server, managing services with systemd, deploying a web app behind Nginx, and checking whether a server is healthy.

## Modules

| Module | What you will learn |
|--------|-------------------|
| **01 - Remote Servers** | What servers are, how to create a VM, SSH in, navigate around, install software, and copy files |
| **02 - Split Screen Workflow** | Terminal multiplexing, the Claude-on-left-server-on-right workflow, following logs, and letting Claude work on a remote server |
| **03 - Server Setup** | Users and permissions, firewalls, installing Nginx, deploying an app, and managing services with systemd |
| **04 - Monitoring** | Checking server health, monitoring disk/memory/CPU, and reading logs |

## Prerequisites

- Completed Phases 01-06 (you should know the terminal, Git, frontend, backend, testing, and infrastructure basics)
- A Linux machine with enough resources to run a virtual machine (4GB RAM minimum, 8GB recommended)
- Claude Code installed and working

## How long will this take?

Expect 8-12 hours. Module 01 (Remote Servers) is the foundation — take your time here. Module 02 (Split Screen Workflow) is short but crucial. Module 03 (Server Setup) is the most hands-on. Module 04 (Monitoring) is a satisfying finish where you see everything running.

## Tips for this phase

- **This is where it gets real.** Working on a remote server is how professional developers spend much of their time. Take it seriously.
- **Type the commands yourself first.** Before letting Claude do things on the server, make sure you understand what the commands do.
- **Mistakes are safe here.** Your VM is a sandbox. If you break it, you can destroy it and create a new one in minutes.
- **The split-screen workflow is the skill.** The specific commands will change from job to job. The ability to work with AI on one side and a server on the other will not.
- **Read error messages carefully.** Server errors are usually clear once you slow down and read them.
