# Teaching: Scrape a Dynamic Page

## Context
The student has learned all the building blocks: launching browsers, navigating, clicking, filling forms, waiting for elements, and capturing output. This capstone challenge puts it all together — they'll scrape real structured data from a JavaScript-rendered page and output clean JSON. Continue working in `workspace/phase-10/playwright-basics/`.

## The challenge
Write a script that scrapes a dynamic (JavaScript-rendered) page, extracts structured data like titles and prices, and saves the results as a clean JSON file.

## Your approach
1. Recap: "You now know how to open a browser, navigate, wait for content, and extract text. Let's combine all of that to scrape a real dynamic page."
2. Ask: "If you wanted to scrape product listings from a page, what data would you extract for each product?" (Expected: name/title, price, description, image URL, link, etc.)
3. Choose a good practice target:
   - `https://quotes.toscrape.com/js/` — quotes rendered by JavaScript (great practice site)
   - Or `https://books.toscrape.com/` — book listings with titles and prices
4. Plan the script structure together:
   - Launch browser and go to the page
   - Wait for the dynamic content to load
   - Find all the repeated elements (e.g., all quote cards, all product cards)
   - Loop through each one and extract the data fields
   - Build an array of objects
   - Save to a JSON file
5. Write the script step by step:
   - Use `page.locator()` to find all items
   - Use `locator.all()` to get an array of elements
   - Use `locator.textContent()`, `locator.getAttribute()` to pull data from each
   - Use `JSON.stringify(data, null, 2)` for pretty-printed JSON
   - Use `fs.writeFileSync()` to save the file
6. Run the script and examine the output JSON together
7. Discuss data cleaning: trimming whitespace, converting prices to numbers, handling missing fields
8. Connect to previous learning: "Remember when we talked about why curl can't scrape dynamic pages? This is exactly that scenario — this page needs JavaScript to render, and Playwright handles it."
9. Ask the quiz questions

## Quiz questions
- Why can't you scrape `quotes.toscrape.com/js/` with a simple HTTP request?
- What does `JSON.stringify(data, null, 2)` do, and why use the extra arguments?
- If a page has 50 product cards, how does your script know to extract data from each one?
- What would you do if the data had extra whitespace or inconsistent formatting?

## Hints (only if stuck)
1. Start by scraping just ONE item first — get the selectors right for a single quote/product before looping through all of them
2. Use browser DevTools (F12) to inspect the page and find the right CSS selectors for the data you want
3. `page.locator('.quote').all()` returns an array of all elements matching `.quote` — then loop through them with `for...of`
4. To save JSON: `const fs = require('fs'); fs.writeFileSync('data.json', JSON.stringify(results, null, 2));`
