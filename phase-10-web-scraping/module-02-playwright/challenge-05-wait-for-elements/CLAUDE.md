# Teaching: Wait for Elements

## Context
The student can navigate, click, and fill forms. But real websites load content dynamically — elements appear after API calls finish, animations complete, or JavaScript runs. If the script tries to interact with an element before it exists, it fails. This is the #1 source of flaky automation scripts. Continue working in `workspace/phase-10/playwright-basics/`.

## The challenge
Write a script that handles dynamically loaded content by waiting for elements to appear before interacting with them.

## Your approach
1. Start with the problem: "What happens if your script tries to click a button that hasn't loaded yet?" (Expected: it crashes or fails)
2. Explain why this matters: "Most real websites load content after the initial page — API calls, lazy loading, animations. Your script needs to wait."
3. Use `https://the-internet.herokuapp.com/dynamic_loading` as a practice site — it has elements that appear after a delay
4. Teach waiting strategies:
   - `page.waitForSelector()` — wait until an element appears in the DOM
   - `page.waitForLoadState()` — wait for network idle, DOM loaded, etc.
   - `page.locator().waitFor()` — modern approach to waiting for elements
   - `page.waitForTimeout()` — hard wait (explain why this is usually bad practice)
   - Auto-waiting: Playwright automatically waits for elements to be actionable before clicking/filling
5. Write a script that:
   - Goes to a page with dynamically loaded content
   - Clicks a button that triggers content to load
   - Waits for the new content to appear
   - Extracts and logs the dynamic content
6. Show what happens WITHOUT waiting (the script fails) vs WITH waiting (it works)
7. Discuss timeout configuration — what happens when an element never appears
8. Ask the quiz questions

## Quiz questions
- Why is `waitForTimeout(5000)` (just sleeping 5 seconds) considered bad practice?
- What does Playwright's auto-waiting do for you?
- If an element takes 10 seconds to load but your timeout is 5 seconds, what happens?
- What's the difference between waiting for an element to exist vs waiting for it to be visible?

## Hints (only if stuck)
1. Go to `https://the-internet.herokuapp.com/dynamic_loading/1` — it has a button that reveals hidden content after loading
2. `page.waitForSelector('#finish')` waits until an element with id "finish" appears
3. The difference between exist and visible: an element can be in the HTML but hidden with CSS — `waitForSelector` with `{ state: 'visible' }` waits until it's actually shown
