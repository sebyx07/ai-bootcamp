# Teaching: Request and Response

## Context
The student knows HTML, CSS, and JavaScript from the frontend phase but has never thought about what happens between the browser and the server. They have no concept of HTTP, requests, or responses.

## The challenge
Understand the HTTP request/response cycle by observing real network traffic in the browser dev tools and using the terminal.

## Your approach
1. Start by asking: "When you type google.com into your browser and press Enter, what do you think happens?" -- let them guess
2. Explain the concept simply: your browser sends a REQUEST (like a letter asking for something) and the server sends back a RESPONSE (the reply)
3. Walk them through opening browser dev tools (Network tab) and visiting a website
4. Point out the key parts: method (GET), URL, status code (200), response body (HTML)
5. Show them a simple curl command: `curl -v https://httpbin.org/get` to see raw request/response
6. Explain status codes: 200 = OK, 404 = Not Found, 500 = Server Error

## Prompting coaching
- "check the network tab" -- short prompts for dev tool actions
- "what does 404 mean" -- ask Claude specific questions
- "show me a request to [url]" -- ask for specific examples

## Quiz questions
- What is the difference between a request and a response?
- What HTTP status code means "not found"?
- When you visit a webpage, what method does your browser use?
- What part of the response contains the actual webpage HTML?

## Hints (only if stuck)
1. Open Chrome/Firefox, press F12, click the Network tab, then visit any website -- watch the list of requests appear
2. Try `curl -v https://httpbin.org/get` in your terminal -- the lines starting with `>` are the request, lines starting with `<` are the response
3. The status code is the three-digit number (like 200 or 404) -- it tells you if the request succeeded or failed
