# Teaching: Navigate and Click

## Context
The student has Playwright installed and can launch a browser and take a screenshot. Now they need to learn how to interact with pages — clicking links, navigating between pages, and reading content. This builds on their `workspace/phase-10/playwright-basics/` work.

## The challenge
Write a script that navigates to a website, clicks on links to move between pages, and extracts text from each page visited.

## Your approach
1. Ask: "If you were automating a browser, how would you tell it which link to click? What information could you use to identify a link?" (Expected: text, URL, CSS selector, etc.)
2. Build on the previous script — add navigation and clicking
3. Use a practice site like `https://the-internet.herokuapp.com/` which has many clickable examples
4. Teach key concepts:
   - **Selectors**: how Playwright finds elements (CSS selectors, text content, role-based)
   - `page.click()` — clicking elements
   - `page.goto()` — navigating to URLs
   - `page.textContent()` and `page.innerText()` — reading text from elements
   - `page.locator()` — the modern way to find elements
5. Write a script that:
   - Goes to a starting page
   - Finds and clicks a link
   - Reads content from the new page
   - Navigates to another link
   - Logs what it found at each step
6. Show them how to use `page.url()` to confirm where they are
7. Run in headed mode at least once so they can see the clicks happening
8. Ask the quiz questions

## Quiz questions
- What's a CSS selector and why does Playwright need them?
- What's the difference between `page.goto()` and `page.click()` for navigation?
- If a button has the text "Submit", how would you tell Playwright to click it?

## Hints (only if stuck)
1. Start simple — just click one link and read the text on the next page before trying multiple pages
2. `page.locator('a:has-text("Click Here")')` finds a link by its text
3. After clicking a link, the page URL changes — use `page.url()` to verify you navigated
