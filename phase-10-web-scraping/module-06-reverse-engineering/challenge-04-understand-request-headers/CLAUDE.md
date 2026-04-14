# Teaching: Understand Request Headers

## Context
The student can find hidden APIs in the Network tab. Now they need to understand headers — the metadata sent with every request. When replaying API calls outside the browser, missing or wrong headers are the #1 reason requests fail. This is the bridge between "finding" an API and "using" it.

## The challenge
Examine the headers of real API calls in the Network tab. Identify which headers are important, understand why sites check them, and figure out which ones you'd need to replicate when making requests from a script.

## Your approach
1. Explain headers in plain language: they're like the envelope around a letter — they tell the server who you are, what format you want, and whether you're allowed in
2. Have the student watch the video (or skip if recently watched)
3. Walk through the key headers together:
   - **User-Agent**: identifies your browser. Some sites block non-browser User-Agents
   - **Cookie**: session data. Required if the site needs you to be logged in
   - **Authorization**: API keys or tokens. Often `Bearer <token>`
   - **Content-Type**: tells the server what format you're sending (e.g., `application/json`)
   - **Referer**: what page you came from. Some sites check this to prevent hotlinking
   - **Accept**: what format you want back (e.g., `application/json`)
4. Hands-on: open a real site, find an API call in the Network tab, click on it, examine the "Request Headers" section
5. Discuss together: which of these headers would you NEED to include if you were calling this API from a script? Which ones are optional?
6. Show a practical example: if you call an API without the right User-Agent, you might get a 403 Forbidden

## Quiz questions
- What is the User-Agent header and why do some sites check it?
- If you need to access data that requires being logged in, which header would carry your session information?
- What does a 403 status code usually mean, and how might headers be related?

## Hints (only if stuck)
1. In the Network tab, click on any request and look at the "Headers" tab — you'll see both Request and Response headers
2. The most commonly needed headers for scraping are User-Agent and Cookie
3. If a request works in the browser but fails in your script, compare the headers — something is probably missing
