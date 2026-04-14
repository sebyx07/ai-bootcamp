# Teaching: What Is Playwright?

## Context
The student has been learning web scraping basics (fetching HTML, parsing with tools like BeautifulSoup or Cheerio). They understand HTTP requests and HTML structure. Now they need to understand why some websites can't be scraped with simple HTTP requests — because the content is rendered by JavaScript in the browser.

## The challenge
The student will learn the concepts behind browser automation: what Playwright is, how it controls a real browser, and why that matters for scraping modern websites. No coding yet — this is a conceptual foundation challenge.

## Your approach
1. Give a short overview: "You've been fetching HTML directly. But many modern sites build their content with JavaScript after the page loads. Playwright lets you control a real browser programmatically — it can click, scroll, wait, and see the same page a human would."
2. Have them watch the video
3. After the video, discuss these key concepts:
   - **Browser automation**: controlling a browser with code instead of a mouse
   - **Headless vs headed**: headless = no visible window (faster, for servers), headed = you see the browser (good for debugging)
   - **Why not just curl/fetch?**: many sites use JavaScript to load content — curl only gets the initial HTML, not what JavaScript builds afterward
   - **Playwright vs Selenium vs Puppeteer**: Playwright is newer, faster, supports multiple browsers, better API
4. Use a concrete example: "Try going to a site like Twitter or Instagram and view the page source — you'll see mostly JavaScript, not the tweets/posts. That's why you need a real browser."
5. Ask the quiz questions to verify understanding

## Quiz questions
- What does "headless" mean when talking about browsers?
- Why would you use Playwright instead of just fetching HTML with curl or a simple HTTP request?
- Name two things Playwright can do that a simple HTTP request cannot.
- When would you want to run a browser in "headed" mode instead of headless?

## Hints (only if stuck)
1. Think about what happens when you visit a modern website — does everything appear instantly, or do some parts load after?
2. "Headless" literally means "without a head" — the head being the visual display/window
3. Try right-clicking on a dynamic website and choosing "View Page Source" vs what you actually see on screen — they're different because JavaScript modifies the page after it loads
