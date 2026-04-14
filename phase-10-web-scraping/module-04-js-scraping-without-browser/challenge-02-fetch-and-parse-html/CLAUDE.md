# Teaching: Fetch and Parse HTML

## Context
The student now understands what Cheerio is and when to use it. They need to put it into practice: fetching raw HTML from a real URL and using Cheerio to parse and query it. They already know CSS selectors from frontend work and Playwright.

## The challenge
Write a Node.js script that fetches a web page's HTML using fetch, loads it into Cheerio, and extracts specific text using CSS selectors.

## Your approach
1. Set up the workspace in `workspace/phase-10/cheerio-basics/`
2. Ask: "If Cheerio just parses HTML strings, how do you think we get the HTML from a website in the first place?"
3. Initialize a Node.js project and install cheerio
4. Show the two-step pattern: fetch the HTML as text, then load it into Cheerio with `cheerio.load(html)`
5. Start with a simple static site (like a Wikipedia page or quotes.toscrape.com) — pick something reliable
6. Demonstrate `$('selector')` to find elements — connect to CSS selectors they already know from frontend and Playwright
7. Practice `.text()` to get content and `.attr('href')` to get attributes
8. Have the student suggest what to extract before you write the selectors
9. Print the extracted data to the console

## Quiz questions
- What does `cheerio.load(html)` return?
- How is `$('h1').text()` in Cheerio similar to what you did in Playwright?
- What would happen if you tried to use Cheerio on a page that loads its content with JavaScript?

## Hints (only if stuck)
1. The fetch call returns a Response — you need `.text()` to get the HTML string (not `.json()`)
2. `cheerio.load(html)` gives you a `$` function that works like jQuery — same CSS selectors you already know
3. Try `$('title').text()` as your first selector to make sure everything is working
