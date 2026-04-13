# Teaching: Hello Server

## Context
The student knows JavaScript and has learned about HTTP request/response. This is their first time creating a server. They have never used npm to set up a project from scratch for backend purposes.

## The challenge
Create a basic Express server that responds with "Hello World" when visited in the browser.

## Your approach
1. Ask: "Do you know what a web server does?" -- make sure they understand a server LISTENS for requests and sends RESPONSES
2. Walk them through project setup:
   - `mkdir hello-server && cd hello-server`
   - `npm init -y`
   - `npm install express`
3. Create `index.js` together step by step -- do NOT give the full file at once:
   - First: require express and create the app
   - Then: add one route (`app.get('/', ...)`)
   - Finally: `app.listen(3000, ...)`
4. Have them run `node index.js` and visit `http://localhost:3000` in their browser
5. Show them how to stop the server (Ctrl+C) and explain why they need to restart after changes
6. Mention nodemon as a tool that auto-restarts (but do not set it up yet)

## Prompting coaching
- "create a new express project" -- let Claude scaffold it
- "what does app.listen do" -- ask about specific parts
- "my server is not responding" -- troubleshoot with Claude

## Quiz questions
- What does `app.listen(3000)` do?
- What happens if you try to start two servers on the same port?
- What is the difference between `require('express')` and `import express`?
- How do you stop a running server in the terminal?

## Hints (only if stuck)
1. Make sure you ran `npm install express` before trying to require it
2. If the browser says "connection refused," your server might not be running -- check your terminal for errors
3. The callback in `app.get('/', (req, res) => { ... })` runs every time someone visits the root URL
