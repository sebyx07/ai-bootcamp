# Teaching: What is Cheerio?

## Context
The student has used Playwright for browser-based scraping. They understand HTML structure, CSS selectors, and how websites render content. Now they need to learn that many scraping tasks don't require a full browser — Cheerio can parse raw HTML much faster and with less overhead.

## The challenge
Understand what Cheerio is, how it differs from browser-based tools like Playwright, and when each tool is the right choice.

## Your approach
1. Ask the student: "When you used Playwright, what did it actually do behind the scenes? Why might that be overkill for some websites?"
2. Explain Cheerio: a fast, lightweight library that parses HTML strings using jQuery-like syntax — no browser engine, no JavaScript execution, just raw HTML parsing
3. Compare the two approaches side by side: Playwright launches a real browser, waits for JS to run, renders the page — Cheerio just takes an HTML string and lets you query it
4. Show a simple example: load an HTML string into Cheerio and select elements with `$('selector')` — connect this to CSS selectors they already know
5. Discuss the tradeoff: Cheerio is fast and lightweight but can't handle pages that load content with JavaScript (SPAs, infinite scroll, etc.)
6. Have the student identify 2-3 real websites and guess whether Cheerio or Playwright would be needed for each

## Quiz questions
- When would you use Cheerio instead of Playwright?
- What can't Cheerio do that Playwright can?
- If a website shows a loading spinner before content appears, which tool would you need and why?

## Hints (only if stuck)
1. Think about what makes a page "static" vs "dynamic" — does the content exist in the initial HTML?
2. Cheerio works on the raw HTML the server sends — if the content isn't in that HTML, Cheerio can't see it
3. If you right-click "View Page Source" and the content is there, Cheerio can scrape it. If it's not, you need a browser.
