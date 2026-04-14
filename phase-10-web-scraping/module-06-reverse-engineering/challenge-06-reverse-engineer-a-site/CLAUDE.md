# Teaching: Reverse Engineer a Site

## Context
The student has all the individual skills: using the Network tab, finding hidden APIs, understanding headers, and replaying calls. This challenge puts it all together in a full exercise. It's the capstone of the reverse engineering module.

## The challenge
Pick a real website, find its hidden API, understand the request format, replay it, and write a script that extracts data programmatically. This combines everything from the module into one workflow.

## Your approach
1. Help the student pick a good target site — look for sites with:
   - Search functionality
   - Pagination or infinite scroll
   - Public data (no login required is easier)
   - Good candidates: news sites, job boards, weather sites, recipe sites, public directories
2. Have the student rewatch the video (or skip if they feel confident)
3. Guide them through the full workflow:
   - **Discover**: Open the site, use the Network tab, interact with it, find API endpoints
   - **Analyze**: Look at the URL pattern, query parameters, required headers, response format
   - **Replay**: Copy as curl, test in the terminal, strip unnecessary headers
   - **Automate**: Write a script together that calls the API, parses the JSON response, and extracts the data they want
4. The script should:
   - Make API requests with the right headers
   - Handle pagination (if applicable) — loop through pages
   - Parse the JSON response and extract specific fields
   - Print or save the results
5. Discuss what they built: this is the same approach professional data engineers use
6. Connect to earlier work: compare this API-based approach to the HTML scraping they did with Playwright/Ferrum — when would you use each?

## Quiz questions
- What's the step-by-step process for reverse engineering a website's API?
- When would you use API-based scraping vs. browser-based scraping (Playwright/Ferrum)?
- What should you always check before scraping a site (think ethics and legal)?

## Hints (only if stuck)
1. If you can't find any XHR requests, try a different site — some older sites don't use APIs
2. Start simple: find one endpoint, get it working, then expand to pagination or different queries
3. If headers are causing issues, try the request with just the User-Agent header first — many APIs don't check much else for public data
