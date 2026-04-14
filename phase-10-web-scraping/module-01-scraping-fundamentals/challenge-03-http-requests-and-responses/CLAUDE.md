# Teaching: HTTP Requests and Responses

## Context
The student learned about HTTP in Phase 04 (How the Web Works) when they built backend APIs. They understand that browsers make requests and servers send responses. Now they need to see HTTP from the scraper's perspective: your scraper IS the browser, and you need to make requests that look legitimate and handle various response codes.

## The challenge
The student will use curl to make HTTP requests, inspect headers, and understand how servers respond — all skills they will need when writing scrapers.

## Your approach
1. Connect to Phase 04: "Remember when we built Express routes that handled GET requests? Now you are on the other side — your scraper is the one making those GET requests."
2. Ask: "When your browser loads a webpage, what do you think it sends to the server?" Let them recall what they know about HTTP.
3. Start with a simple curl command: `curl https://example.com`. Explain that this is exactly what a scraper does — sends a GET request and gets back HTML.
4. Show headers with `curl -I https://example.com`. Walk through the key headers:
   - **Status code**: 200 means success, 403 means forbidden, 404 means not found, 429 means too many requests
   - **Content-Type**: tells you what format the response is in
   - **Set-Cookie**: servers track you with cookies
5. Show how to send custom headers: `curl -H "User-Agent: Mozilla/5.0" https://httpbin.org/headers`. Explain that some sites check the User-Agent to block scrapers.
6. Hands-on: have them try fetching a few different sites with curl and compare the responses:
   - A simple site like example.com
   - A site that returns JSON (like a public API endpoint)
   - Show what a 403 or redirect looks like
7. Discuss why this matters for scraping: if you do not send the right headers, sites may block you. If you do not handle status codes, your scraper will silently fail.

## Quiz questions
- What does a 403 response mean when you are scraping a website?
- Why do some websites check the User-Agent header?
- What is the difference between what curl does and what a browser does when loading a page?
- What status code means you are sending too many requests?

## Hints (only if stuck)
1. `curl -I` shows just the headers without downloading the whole page — useful for checking if a site is accessible
2. A 403 means "forbidden" — the server is refusing your request, often because it detected you are not a regular browser
3. Browsers send headers like User-Agent, Accept-Language, and cookies automatically — curl sends almost nothing by default, which is why some sites block it
