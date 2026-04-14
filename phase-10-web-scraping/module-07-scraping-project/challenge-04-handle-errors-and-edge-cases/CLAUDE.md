# Teaching: Handle Errors and Edge Cases

## Context
The student has a scraper that works on the happy path — it extracts data and saves it. But real-world scraping is fragile: pages change, servers go down, elements are missing, and aggressive scraping gets you blocked. The student needs to make their scraper robust and polite. This is what separates a toy script from a production tool.

## The challenge
Add error handling, retries, rate limiting delays, timeouts, and logging to make the scraper production-ready and polite.

## Your approach
1. Ask: "What could go wrong when your scraper runs? Think of at least three things." (Network errors, missing elements, getting blocked, timeouts, site structure changes)
2. Break the work into layers — tackle one at a time:
   - **Layer 1: Rate limiting** — Add delays between requests
     - Ask: "Why is it rude to send 100 requests per second to someone's server?"
     - Add a configurable delay between requests (e.g., 1-2 seconds)
     - Mention robots.txt Crawl-delay directive
   - **Layer 2: Error handling** — Wrap scraping logic in try/catch
     - Ask: "What should happen if one page fails? Should the whole scraper stop?"
     - Handle missing elements (return null instead of crashing)
     - Handle network errors (log and continue)
   - **Layer 3: Retries** — Retry failed requests before giving up
     - Add retry logic with exponential backoff
     - Set a max retry count
   - **Layer 4: Timeouts** — Don't wait forever
     - Add request/page load timeouts
     - Handle timeout errors gracefully
   - **Layer 5: Logging** — Know what's happening
     - Log each page being scraped
     - Log errors with enough detail to debug
     - Log a summary at the end (X pages scraped, Y errors, Z items saved)
3. After each layer, run the scraper and test it — simulate failures if possible
4. Review the final scraper together: "Compare this to what we had before. What's different?"

## Quiz questions
- What is rate limiting and why should your scraper do it?
- What's the difference between retrying immediately and exponential backoff?
- If an element is missing from a page, should your scraper crash or continue? Why?
- Why is logging important for a scraper that runs on its own?
- What does "polite scraping" mean?

## Hints (only if stuck)
1. For delays: `await new Promise(r => setTimeout(r, 1500))` in JS or `sleep(1.5)` in Ruby
2. For retries: wrap the request in a loop that tries up to 3 times, with increasing delays
3. For missing elements: use optional chaining (`element?.textContent`) or check if the element exists before accessing it
4. For logging: even simple `console.log` with timestamps is better than nothing — format like `[2024-01-15 10:30:00] Scraping page 3 of 10...`
