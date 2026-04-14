# Teaching: Build the Scraper

## Context
The student has a scraping plan from challenge-01 — a target site, the data they want, and an idea of the structure. They have used Playwright, Ferrum, and Cheerio in earlier modules. Now they need to pick the right tool and build the real thing. All work goes in `workspace/phase-10/scraping-project/`.

## The challenge
Build a working scraper based on the plan from challenge-01. Choose the right tool for the job, write the code, and extract the planned data.

## Your approach
1. Ask: "Looking at your target site, does it load data with JavaScript or is the HTML already there when the page loads? How would you check?"
2. Based on their answer, guide them to the right tool choice:
   - Static HTML → Cheerio (lightweight, fast)
   - JavaScript-rendered content → Playwright or Ferrum (browser automation)
   - Discuss tradeoffs: speed vs capability, Node vs Ruby
3. Ask: "What's the first thing we should do before writing the scraper?" (Check robots.txt, understand the page structure)
4. Open the target site together — look at the HTML structure, identify selectors
5. Start building incrementally — don't write the whole scraper at once:
   - Step 1: Navigate to the page and confirm it loads
   - Step 2: Extract one piece of data (prove the selector works)
   - Step 3: Extract all the planned data fields
   - Step 4: Handle pagination or multiple pages if needed
6. Run the scraper after each step — test as you go
7. Ask the student to read any errors before you fix them
8. Once it works, review the output together: "Does this match what you planned?"

## Quiz questions
- Why did you choose [tool] over the other options?
- What would happen if the site changed its HTML structure tomorrow?
- What does your scraper do if a particular element is missing from a page?

## Hints (only if stuck)
1. Check robots.txt first — navigate to `yoursite.com/robots.txt` in a browser
2. Use browser DevTools to find the right CSS selectors — right-click an element and inspect it
3. Start with extracting just one item before trying to get them all
4. If Playwright/Ferrum pages look empty, the site might need time to load — add a wait
