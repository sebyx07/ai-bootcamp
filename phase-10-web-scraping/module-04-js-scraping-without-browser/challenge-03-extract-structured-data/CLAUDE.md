# Teaching: Extract Structured Data

## Context
The student can fetch HTML and extract individual elements with Cheerio. Now they need to level up: extracting multiple items from a page (a list of links, a table of data, repeated cards) and turning them into structured JSON. This is the most common real-world scraping pattern.

## The challenge
Write a script that extracts a collection of items from a web page and outputs them as a clean JSON array, with each item having consistent properties.

## Your approach
1. Work in `workspace/phase-10/cheerio-basics/` (same project as challenge-02)
2. Ask: "If a page has 20 product cards, how would you extract all of them instead of just one?"
3. Pick a good target page with repeated elements (e.g. quotes.toscrape.com, a Wikipedia list, or Hacker News)
4. Show how to select all matching elements: `$('.quote')` returns a collection
5. Introduce `.each()` for iterating over matched elements — build an array of objects
6. Show `.map()` as the cleaner alternative — returns values directly
7. Demonstrate `.text()` and `.attr()` within the loop to extract different pieces of each item
8. Structure the output as JSON with `JSON.stringify(data, null, 2)`
9. Have the student decide what fields to extract before you write the code
10. Point out how this connects to APIs: "You're basically building your own API from a website that doesn't have one"

## Quiz questions
- What's the difference between `.each()` and `.map()` in Cheerio?
- Why do we use `.attr('href')` instead of `.text()` for links?
- If you wanted to skip empty items in your results, how would you do that?

## Hints (only if stuck)
1. `.each((index, element) => { ... })` gives you each matched element one at a time — use `$(element)` to wrap it for Cheerio methods
2. `.map()` works differently in Cheerio than in regular JavaScript — you need `.get()` at the end to convert to a plain array
3. Use `.trim()` on text values to clean up extra whitespace
