# Teaching: Scrape a Real Site

## Context
The student has learned all the Ferrum fundamentals: launching browsers, extracting data, interacting with pages, and handling JavaScript. They also did similar work with Playwright earlier. This is the capstone challenge — put it all together on a real site and output clean JSON. Then reflect on Ferrum vs Playwright.

## The challenge
Write a complete Ruby script that scrapes structured data from a real website (like books, products, or articles), handles errors gracefully, and saves the results as a JSON file. Then compare the experience with Playwright. Work in `workspace/phase-10/ferrum-basics/`.

## Your approach
1. Ask: "You've now learned all the pieces — navigating, extracting, interacting, waiting for JS. If you had to scrape a list of books from a website, what steps would your script need?" (let them plan the flow)
2. Pick a scraping-friendly site like https://books.toscrape.com or https://quotes.toscrape.com
3. Plan the script structure together:
   - Launch browser
   - Navigate to the site
   - Wait for content to load
   - Find all items using CSS selectors
   - Loop through and extract data into a Ruby array of hashes
   - Convert to JSON and save to file
   - Handle errors with begin/rescue
   - Quit the browser
4. Let them suggest which data to extract (title, price, rating, etc.)
5. Write the script — explain how `require 'json'` and `JSON.pretty_generate` work for clean output
6. Run it and inspect the JSON file together
7. After it works, have the Ferrum vs Playwright discussion:
   - Ferrum: great for Ruby projects, uses CDP directly, simpler API
   - Playwright: cross-browser, more mature ecosystem, better for JS/Python shops
   - Both: headless browser automation, can handle JS-rendered pages
8. Quiz them

## Quiz questions
- What Ruby method converts a hash/array to JSON?
- Why do we wrap the whole script in a begin/rescue/ensure block?
- When would you choose Ferrum over Playwright for a scraping project?
- When would you choose Playwright over Ferrum?
- What's the most important thing to do at the end of any browser automation script?

## Hints (only if stuck)
1. Use `require 'json'` at the top — then `JSON.pretty_generate(data)` to make readable JSON
2. Use `File.write("output.json", json_string)` to save to a file
3. Put `browser.quit` in an `ensure` block so the browser always closes, even if there's an error
4. Start simple — extract just titles first, then add more fields once that works
5. If the site has multiple pages, start with just page one — pagination can come later
