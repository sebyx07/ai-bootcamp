# Teaching: What Is Auth

## Context
The student has built a blog but anyone can create, edit, or delete posts. They have no concept of "logged in users." This challenge introduces the CONCEPTS before the implementation.

## The challenge
Understand authentication vs authorization, why HTTP is stateless, and how auth solves the problem.

## Your approach
1. Ask: "Right now, anyone can delete any article on your blog. Is that a problem?" -- yes, obviously
2. Explain the two concepts:
   - **Authentication**: "WHO are you?" -- proving your identity (login)
   - **Authorization**: "WHAT can you do?" -- checking permissions (can this user edit this post?)
3. Explain the stateless problem:
   - HTTP has no memory -- each request is independent
   - The server does not remember you between requests
   - So how does a website know you are logged in? (sessions, cookies, tokens)
4. Overview of common auth methods:
   - Username + password (most common for web apps)
   - OAuth ("Login with Google/GitHub")
   - API keys (for machine-to-machine)
   - Multi-factor (password + phone code)
5. Discuss real-world examples:
   - Authentication: logging into your email
   - Authorization: you can see your emails but not your friend's
6. Preview what they will build: a login/signup system for the blog

## Prompting coaching
- "what is the difference between authentication and authorization" -- ask for clear definitions
- "how does a website remember me" -- explore the problem
- "give me a real world example" -- make it concrete

## Quiz questions
- Is "checking if a user is an admin" authentication or authorization?
- Why does HTTP being stateless make authentication harder?
- What are cookies used for in authentication?
- Why should you never store plain-text passwords?

## Hints (only if stuck)
1. Authentication = identity (who), Authorization = permissions (what)
2. HTTP is stateless: each request knows nothing about previous requests -- sessions and cookies solve this
3. Think of authentication like showing your ID at a bar, and authorization like the bouncer checking if you are on the VIP list
