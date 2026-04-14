# Teaching: HTML Structure Revisited

## Context
The student learned HTML and CSS back in Phase 03. They know what tags, classes, and IDs are. Now they need to see HTML from a different angle: not as something they build, but as something they read and target. This is the skill that makes scraping possible — if you cannot find the right selector, you cannot extract the right data.

## The challenge
The student will open real websites in DevTools, practice finding CSS selectors for specific elements, and build confidence reading someone else's HTML structure.

## Your approach
1. Start by connecting to Phase 03: "Remember when you wrote HTML with classes and IDs? Now you are on the other side — reading someone else's HTML to find the data you want."
2. Ask: "If I wanted to grab every product title from a shopping page, what would I need to know about the HTML?" Let them think about it.
3. Review CSS selectors from a scraping perspective:
   - Tag selectors: `h1`, `p`, `a`
   - Class selectors: `.product-title`, `.price`
   - ID selectors: `#main-content`
   - Nested selectors: `div.content a`, `ul.results li`
   - Attribute selectors: `a[href*="product"]`
4. Hands-on exercise: have them open a real website (suggest Wikipedia, Hacker News, or a news site) in their browser and open DevTools (F12 or right-click > Inspect).
5. Give them specific tasks:
   - "Find the selector for the main headline"
   - "Find the selector that would grab all the links in the navigation"
   - "Find the selector for a specific piece of data on the page"
6. Teach the DevTools trick: right-click an element > Inspect, then right-click the highlighted HTML > Copy > Copy selector. Explain that auto-generated selectors are often too specific and fragile.
7. Discuss why good selectors matter for scraping: pages change, so you want selectors that are stable (class names) not fragile (nth-child chains).

## Quiz questions
- How would you select all links inside a div with class "content"?
- What is the difference between `.price` and `#price` as selectors?
- Why might an auto-generated CSS selector from DevTools be a bad choice for scraping?

## Hints (only if stuck)
1. Open DevTools with F12, then use the element picker (top-left arrow icon) to click on any element and see its HTML
2. `div.content a` means "find all `a` tags that are inside a `div` with class `content`"
3. Classes can appear on many elements (good for grabbing lists of things), IDs should be unique (good for grabbing one specific thing)
