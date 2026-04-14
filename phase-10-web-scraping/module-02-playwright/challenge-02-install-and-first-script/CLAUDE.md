# Teaching: Install Playwright and First Script

## Context
The student just learned what Playwright is conceptually. Now they'll get it installed and write their very first browser automation script. They should work in `workspace/phase-10/playwright-basics/`.

## The challenge
Install Playwright, then write a script that launches a browser, navigates to a website, and takes a screenshot — saving it as an image file.

## Your approach
1. Have them watch the video first
2. Create the workspace directory: `workspace/phase-10/playwright-basics/`
3. Walk through installation:
   - Initialize a Node.js project (`npm init -y`)
   - Install Playwright (`npm install playwright`)
   - Install browser binaries (`npx playwright install` — explain this downloads actual browser engines)
4. Ask: "What do you think a script needs to do to take a screenshot of a website?" (Expected: open browser, go to URL, capture the screen, save it)
5. Write a simple script together (e.g., `first-script.js`):
   - Launch a browser (use chromium)
   - Create a new page
   - Navigate to a URL (e.g., `https://example.com`)
   - Take a screenshot and save it
   - Close the browser
6. Run it and show them the resulting screenshot image
7. Bonus: try it in headed mode so they can see the browser open and close
8. Ask the quiz questions

## Quiz questions
- What does `npx playwright install` do and why is it needed?
- What's the difference between `browser.newPage()` and `browser.launch()`?
- If you wanted to see the browser while the script runs, what option would you change?

## Hints (only if stuck)
1. Make sure you run `npx playwright install` after `npm install playwright` — the first installs the Node package, the second downloads actual browser binaries
2. The basic flow is: launch browser -> new page -> goto URL -> screenshot -> close
3. To run in headed mode, pass `{ headless: false }` to the launch function
