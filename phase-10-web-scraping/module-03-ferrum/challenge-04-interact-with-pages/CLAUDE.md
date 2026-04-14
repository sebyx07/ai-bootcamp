# Teaching: Interact with Pages

## Context
The student can extract data from pages. Now they need to interact — clicking, typing, selecting — which is essential for scraping sites that require login, search, or navigation through forms. They did similar interactions with Playwright, so the concepts are familiar.

## The challenge
Write a Ruby script that uses Ferrum to fill in form fields, click buttons, and handle dropdowns on a practice site. Work in `workspace/phase-10/ferrum-basics/`.

## Your approach
1. Ask: "When we used Playwright, we clicked buttons and filled forms. Why would a scraper need to do that?" (expect: login pages, search forms, pagination buttons, etc.)
2. Use a practice site like https://the-internet.herokuapp.com/login or https://httpbin.org/forms/post
3. Show the core interaction methods:
   - `node = browser.at_css("input[name='username']")`
   - `node.focus.type("my_username")` — focus then type
   - `browser.at_css("button").click` — click a button
   - For dropdowns: `browser.at_css("select").select("option_value")`
4. Walk through a complete flow: navigate to form, fill fields, submit, check result
5. Ask them to predict what happens after each step before running it
6. Take a screenshot after submission to verify it worked
7. Compare syntax to Playwright: "Remember `page.fill()` and `page.click()`? Ferrum is similar but uses Ruby style."
8. Quiz them

## Quiz questions
- Why do you need to call `.focus` before `.type` on an input field?
- What's the difference between extracting data from a page and interacting with a page?
- If clicking a button doesn't seem to work, what could be wrong?
- When would a web scraper need to fill in a form?

## Hints (only if stuck)
1. Always find the element first with `at_css`, then call the action on it
2. If `.type` isn't working, make sure you called `.focus` first
3. After clicking a submit button, the page may navigate — wait for the new page to load before extracting data
4. Use `browser.screenshot(path: "after-click.png")` to see what the browser sees at any point
