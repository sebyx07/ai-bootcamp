# Teaching: Screenshots and PDFs

## Context
The student knows how to navigate, interact, and wait for elements. Now they'll learn to capture visual output — full-page screenshots, element-specific screenshots, and PDFs. This is useful for documentation, visual testing, archiving pages, and reporting. Continue working in `workspace/phase-10/playwright-basics/`.

## The challenge
Write a script that captures different types of screenshots and generates a PDF from a web page.

## Your approach
1. Ask: "When would you want to save a screenshot or PDF of a web page?" (Expected: archiving, testing, documentation, proof, reports)
2. Start with what they already know — they took a basic screenshot in challenge 02
3. Teach the different capture modes:
   - `page.screenshot()` — viewport screenshot (just what's visible)
   - `page.screenshot({ fullPage: true })` — captures the entire scrollable page
   - `locator.screenshot()` — captures just a specific element
   - `page.pdf()` — generates a PDF (note: only works in Chromium, headless mode)
4. Write a script that visits a long page (e.g., a Wikipedia article) and:
   - Takes a viewport screenshot
   - Takes a full-page screenshot (compare the file sizes!)
   - Captures a specific element (e.g., just a heading or an image)
   - Generates a PDF of the page
5. Discuss options:
   - Image format (`png` vs `jpeg`) and quality settings
   - PDF options (format, margins, headers/footers)
   - Path for saving files
6. Show the outputs — open the files so they can see the difference between viewport and full-page
7. Ask the quiz questions

## Quiz questions
- What's the difference between a viewport screenshot and a full-page screenshot?
- Why does PDF generation only work in headless Chromium?
- When would you want to screenshot just one element instead of the whole page?

## Hints (only if stuck)
1. `page.screenshot({ path: 'full.png', fullPage: true })` captures the entire scrollable page
2. For element screenshots, first get a locator: `page.locator('h1').screenshot({ path: 'heading.png' })`
3. PDF generation requires headless Chromium — `chromium.launch()` without `headless: false`
