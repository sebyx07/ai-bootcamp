# Teaching: Plan Your Scraper

## Context
The student has learned scraping fundamentals, Playwright, Ferrum, and reverse engineering. Now they're going to build a real scraping project from scratch. Planning is the first and most important step — a bad plan leads to wasted effort. This is also where ethics matter most.

## The challenge
Pick a real website to scrape, decide exactly what data to extract, choose the right tool (Playwright, Ferrum, or direct API calls), and write a plan before writing any code.

## Your approach
1. Discuss ethical scraping first:
   - Check robots.txt — does the site allow scraping?
   - Check Terms of Service — some sites explicitly prohibit it
   - Is the data publicly available? Don't scrape private/personal data
   - Respect rate limits — don't hammer servers
   - Good targets: public data, educational sites, your own projects
2. Have the student watch the video
3. Help them pick a target — brainstorm together. Good project ideas:
   - Job listings from a public job board
   - Product prices from a comparison site
   - Weather data from a forecast site
   - Recipe data from a cooking site
   - Public event listings
4. Define the data points: what specific fields do they want? (title, price, date, URL, etc.)
5. Choose the tool together:
   - **Direct API calls**: if you found a hidden API in the previous module
   - **Playwright (Node.js)**: if the site needs JavaScript rendering and you're comfortable with JS
   - **Ferrum (Ruby)**: if the site needs JavaScript rendering and you prefer Ruby
6. Write the plan in a file in the workspace — this becomes the blueprint for the next challenges
7. Connect to previous work: reference the reverse engineering module — did they find any APIs they want to use?

## Quiz questions
- Why is it important to check robots.txt before scraping a site?
- What factors help you decide between using direct API calls vs. browser-based scraping?
- What are three specific data points you want to extract and why?

## Hints (only if stuck)
1. If you can't think of a site, start with something you personally use — what data would be useful to have in a spreadsheet?
2. Check if the site has a hidden API first (from the reverse engineering module) — that's almost always easier than scraping HTML
3. Keep the scope small for your first project — 1 page type, 3-5 data fields, no login required
