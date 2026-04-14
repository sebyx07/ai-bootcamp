# Teaching: Puppeteer vs Playwright

## Context
The student has used Playwright for browser scraping and Cheerio for static HTML parsing. Now they need to understand the full landscape of JavaScript scraping tools. They should understand that Puppeteer (by Google) and Playwright (by Microsoft) are both browser automation tools with different strengths, and know how to choose the right tool for any scraping job.

## The challenge
Compare Puppeteer and Playwright by doing the same scraping task with both tools, then articulate the tradeoffs between Cheerio, Puppeteer, and Playwright.

## Your approach
1. Ask: "You've now used Cheerio and Playwright. What do you think the differences might be between browser-based tools?"
2. Give a brief history: Puppeteer came first (Google, Chrome-only), Playwright was built by the same team after they moved to Microsoft (multi-browser)
3. Map out the three tiers: Cheerio (no browser, fastest, static only) -> Puppeteer (Chrome browser, good for Chrome-specific tasks) -> Playwright (multi-browser, best API, most features)
4. Set up a hands-on comparison in `workspace/phase-10/cheerio-basics/` or a new subfolder
5. Install puppeteer alongside the existing playwright setup
6. Write the same scraping task with both Puppeteer and Playwright — keep it simple so the API differences stand out
7. Compare the code side by side: initialization, navigation, selectors, waiting, cleanup
8. Discuss real-world considerations: Playwright has better auto-waiting, multi-browser support, and is more actively developed; Puppeteer is simpler for Chrome-only tasks
9. Create a decision flowchart together: static page -> Cheerio; dynamic page, Chrome only -> Puppeteer; dynamic page, need reliability -> Playwright

## Quiz questions
- What's the main advantage Playwright has over Puppeteer?
- When might you still choose Puppeteer over Playwright?
- If you need to scrape a page that works fine in Chrome and you want the simplest setup, which tool would you pick?
- Why would you ever use Cheerio when Playwright can do everything Cheerio does?

## Hints (only if stuck)
1. Both Puppeteer and Playwright control a real browser — the difference is which browsers and how nice the API is
2. Playwright was literally built by the Puppeteer team — think of it as "Puppeteer 2.0" with more features
3. Performance matters: Cheerio processes HTML in milliseconds, browser tools take seconds to launch and navigate
