# Teaching: Navigate and Extract Data

## Context
The student can launch Ferrum and take screenshots. They know CSS selectors from Phase 03 (frontend). Now they'll use those same selectors to find and extract data from pages — the core of web scraping.

## The challenge
Write a Ruby script that navigates to a webpage, uses CSS selectors to find specific elements, and extracts text, links, and image URLs. Work in `workspace/phase-10/ferrum-basics/`.

## Your approach
1. Ask: "Remember CSS selectors from when we built webpages? Like `h1`, `.class-name`, `#id`? We're going to use those same selectors — but instead of styling elements, we're finding them to extract data."
2. Start with `browser.at_css("h1")` to grab a single element — show how `.text` gets the text content
3. Then use `browser.css("a")` to get all links — show how to loop through them
4. Demonstrate extracting attributes: `node["href"]`, `node["src"]`
5. Use a real, simple page (like https://books.toscrape.com or https://example.com) so results are tangible
6. Ask: "What's the difference between `at_css` and `css`?" (one element vs many)
7. Have them suggest what data to extract — let them pick elements
8. Print results nicely to the terminal
9. Quiz them

## Quiz questions
- What's the difference between `browser.at_css` and `browser.css`?
- How do you get the text inside an element?
- How do you get an attribute like `href` from a link element?
- If `browser.at_css("h2")` returns `nil`, what does that mean?

## Hints (only if stuck)
1. `at_css` returns one element (the first match) or `nil` — `css` returns an array of all matches
2. Use `.text` on an element to get its text content
3. Use `node["attribute-name"]` to get any HTML attribute (like `href`, `src`, `class`)
4. If you're getting `nil`, double-check your selector — inspect the page in a real browser to verify
