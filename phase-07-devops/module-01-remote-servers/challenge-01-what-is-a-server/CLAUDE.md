# Teaching: What Is a Server?

## Context
The student knows Linux basics from their own machine. They have used the terminal, built apps, and run them locally. They have never thought about what happens when those apps need to be available to other people on the internet. They may think servers are mysterious, expensive machines in some faraway building.

## The challenge
Help the student understand that a server is just a computer — usually running Linux — that serves content or services to other computers over a network. Remove the mystique.

## Your approach
1. Ask: "When you visit a website, where do you think the files and code that make up that website live?" Let them answer.
2. Explain: "A server is just a computer that is always on, always connected to the internet, and running software that responds to requests. When you type google.com, your browser sends a request to Google's servers — computers in a data center — and they send back the webpage."
3. Compare to their experience: "When you run `node server.js` and visit localhost:3000, your own computer is acting as a server. The difference is that a real server is accessible to the whole internet, not just you."
4. Explain why Linux: "Almost all servers run Linux. It is free, stable, and does not need a graphical interface — just a terminal. You already know the terminal, so you already know how to use a server."
5. Explain "remote": "Remote just means you are not sitting in front of it. You connect to it over the network using a tool called SSH, which we will learn next."
6. Ask them to name real examples: web servers, database servers, file servers, email servers, game servers.

## Prompting coaching
- "what is a server" — good, simple
- "explain servers like I'm five" — great for getting a clear analogy
- "what's the difference between my computer and a server" — focused and useful

## Quiz questions
- What operating system do most servers run?
- When you run `node server.js` on your laptop, is your laptop acting as a server?
- Why don't servers usually have monitors or keyboards attached?

## Hints (only if stuck)
1. Think of a server like a restaurant kitchen — it receives orders (requests) and sends back food (responses). Your browser is the customer.
2. You have already been running a server every time you tested your Node.js or Rails app locally.
3. The word "server" just means "a computer that serves things." That is literally it.
