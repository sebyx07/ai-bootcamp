# Teaching: Install Ferrum and First Script

## Context
The student knows what Ferrum is from challenge-01. They know Ruby basics from Phase 04 (gems, require, running scripts). They've used Playwright before, so the concept of browser automation is familiar. Now they'll get hands-on with Ferrum.

## The challenge
Install the Ferrum gem, then write a Ruby script that launches a headless Chrome browser, navigates to a website, and saves a screenshot. Work in `workspace/phase-10/ferrum-basics/`.

## Your approach
1. Ask: "Remember installing npm packages for Playwright? How do you think we install a Ruby gem?" (connect to Phase 04 Ruby knowledge)
2. Install Ferrum: `gem install ferrum`
3. Create the workspace directory: `workspace/phase-10/ferrum-basics/`
4. Before writing the script, ask: "What steps do you think our script needs to do? Think about what we did with Playwright." (expect: open browser, go to page, take screenshot, close browser)
5. Write a simple script together — something like:
   - `require 'ferrum'`
   - `browser = Ferrum::Browser.new`
   - `browser.goto("https://example.com")`
   - `browser.screenshot(path: "screenshot.png")`
   - `browser.quit`
6. Run it and verify the screenshot was saved
7. Ask them to compare this to the Playwright equivalent — it's very similar in structure
8. Quiz them

## Quiz questions
- What does `Ferrum::Browser.new` do?
- Why do we call `browser.quit` at the end?
- What would happen if you forgot `require 'ferrum'` at the top of the script?
- How is `gem install ferrum` similar to `npm install playwright`?

## Hints (only if stuck)
1. Make sure Chrome/Chromium is installed on the system — Ferrum needs a real browser to control
2. If you get a "browser not found" error, try `Ferrum::Browser.new(browser_path: "/usr/bin/chromium-browser")`
3. The screenshot method takes a `path:` option — that's where the file gets saved
