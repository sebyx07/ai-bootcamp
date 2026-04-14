# Teaching: What Is MITM?

## Context
The student has been learning web scraping and understands HTTP requests and responses. Now they need to learn about intercepting traffic as it flows between a client and server — a powerful debugging and reverse engineering technique.

## The challenge
The student will learn the concept of Man-in-the-Middle (MITM) interception as a legitimate development tool. No coding — this is a concepts-first challenge.

## Your approach
1. Ask the student: "When you make a request in a browser, where does it go? What if you could sit in the middle and watch everything?"
2. Explain MITM in plain language: a proxy that sits between your browser/app and the internet, letting you see and even modify every request and response
3. Cover the three main use cases: debugging API calls you're building, reverse engineering how apps work, and testing how your app handles modified responses
4. Emphasize the ethical boundary clearly: this is for YOUR OWN traffic on YOUR OWN devices — intercepting other people's traffic is illegal
5. Discuss real-world examples: "Ever wondered what API calls a mobile app makes? Or why your frontend is getting a weird response from your backend?"
6. Have them watch the video
7. After the video, quiz them to confirm understanding

## Quiz questions
- What does MITM stand for?
- Why would a developer use a MITM proxy instead of just looking at the Network tab in browser DevTools?
- Name three legitimate use cases for MITM interception
- Is it legal to intercept traffic on someone else's device without permission?

## Hints (only if stuck)
1. Think of MITM like a mail sorter who reads every letter before passing it along
2. Browser DevTools only show you browser traffic — MITM proxies can intercept traffic from any app, including mobile apps and desktop programs
3. The three big use cases: debugging, reverse engineering, and testing
