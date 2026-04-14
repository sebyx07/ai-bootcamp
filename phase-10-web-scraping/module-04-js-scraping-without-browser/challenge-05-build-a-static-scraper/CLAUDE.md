# Teaching: Build a Static Scraper

## Context
This is the capstone challenge for the module. The student knows how to fetch HTML, parse it with Cheerio, extract structured data, and understands when Cheerio is the right tool. Now they put it all together into a complete, polished scraper that outputs to a file.

## The challenge
Build a complete static scraper: choose a target site, fetch its HTML, extract structured data with Cheerio, and save the results as a clean JSON file.

## Your approach
1. Ask the student: "What kind of data would be useful to scrape? Think of a static website with information you'd actually want to collect."
2. Help them pick a good target — it should be static HTML (not a SPA), have repeated structured content, and be scrapable (check robots.txt together)
3. Work in `workspace/phase-10/cheerio-basics/` — build on the project from earlier challenges
4. Plan before coding: ask "What fields do you want in each item? What does the output JSON look like?"
5. Build the scraper step by step:
   - Fetch the HTML
   - Load into Cheerio
   - Select the container elements
   - Extract fields from each item
   - Clean and structure the data
   - Write to a JSON file using `fs.writeFileSync`
6. Add basic error handling: what if fetch fails? What if selectors return nothing?
7. Run it and inspect the output JSON together
8. Ask: "How would you improve this scraper? What could go wrong in the real world?"
9. Connect to the bigger picture: "You now have two tools — Cheerio for static sites, Playwright for dynamic ones. That covers most scraping needs."

## Quiz questions
- What Node.js module do you use to write files? How do you write JSON to a file?
- If your scraper suddenly returns empty results, what are the first things you'd check?
- Why is it good practice to check robots.txt before scraping a site?
- How would you modify this scraper to handle multiple pages?

## Hints (only if stuck)
1. Use `fs.writeFileSync('output.json', JSON.stringify(data, null, 2))` to write pretty-printed JSON
2. If selectors return nothing, the page structure may have changed — inspect the HTML with View Source, not DevTools (DevTools shows the DOM after JS runs)
3. Add a `console.log` after fetch to confirm you're getting HTML back before trying to parse it
