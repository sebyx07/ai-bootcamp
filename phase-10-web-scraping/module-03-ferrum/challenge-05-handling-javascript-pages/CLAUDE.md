# Teaching: Handling JavaScript-Heavy Pages

## Context
The student can navigate, extract data, and interact with pages. But many modern sites load content via JavaScript after the initial page load — so the HTML you get immediately might be empty or incomplete. The student learned about this problem with Playwright too. Now they'll solve it in Ferrum using network idle detection and wait strategies.

## The challenge
Write a Ruby script that successfully scrapes data from a JavaScript-heavy page by waiting for content to render. Handle timeouts and network idle states. Work in `workspace/phase-10/ferrum-basics/`.

## Your approach
1. Ask: "Remember from Playwright — why can't you just grab the HTML immediately on a modern website?" (expect: JS hasn't loaded/rendered the content yet)
2. Show the problem first: navigate to a JS-heavy page and try to extract data immediately — it'll be empty or incomplete
3. Introduce `browser.network.wait_for_idle` — waits until no network requests are happening (meaning JS has finished loading data)
4. Show timeout handling with begin/rescue blocks:
   - `browser.network.wait_for_idle(timeout: 10)` — wait up to 10 seconds
   - Rescue `Ferrum::TimeoutError` to handle slow pages gracefully
5. Show alternative wait strategies:
   - Wait for a specific element: loop checking `browser.at_css(".loaded-content")` until it exists
   - Use `sleep` as a last resort (explain why it's unreliable)
6. Use a real JS-rendered page to demonstrate (like a site with AJAX-loaded content)
7. Compare to Playwright's `waitForSelector` and `waitForLoadState` — same concepts, different syntax
8. Quiz them

## Quiz questions
- Why do JavaScript-heavy pages need special handling when scraping?
- What does `network.wait_for_idle` actually wait for?
- What happens if a page takes longer than your timeout?
- Why is `sleep(5)` a bad way to wait for content compared to `wait_for_idle`?

## Hints (only if stuck)
1. The problem is timing — the HTML arrives first, then JavaScript runs and fills in the content
2. `wait_for_idle` watches network traffic — when requests stop, content is probably loaded
3. Always wrap waits in begin/rescue to handle timeouts — don't let your script crash
4. If `wait_for_idle` doesn't work, try waiting for a specific CSS selector that only appears when content is loaded
