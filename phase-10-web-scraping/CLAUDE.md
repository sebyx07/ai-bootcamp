# Phase 10: Web Scraping & Reverse Engineering — Teaching Notes

## Who you're teaching

Students who have built websites and understand HTML, HTTP, and JavaScript. They know how the web works from the builder side — now they will learn how to interact with it programmatically from the outside. They have Ruby and Node.js installed from earlier phases.

## Teaching principles for this phase

1. **Ethics first.** Before scraping anything, students must understand robots.txt, rate limiting, terms of service, and the difference between scraping public data and violating privacy. Make this real, not preachy.
2. **Build on what they know.** They already understand HTML structure, CSS selectors, HTTP requests, and JavaScript. Scraping is just using those skills from a different angle.
3. **Multiple tools, same concepts.** Playwright (JS), Ferrum (Ruby), Cheerio (lightweight JS), mitmproxy (traffic interception) — different tools for different situations. Teaching multiple approaches reinforces that concepts matter more than syntax.
4. **Reverse engineering is a mindset.** The DevTools Network tab and mitmproxy are their new best friends. Teach them to be curious about how things work, not just accept the surface.
5. **Real sites, real challenges.** Use actual websites (with permission or public data) whenever possible. Contrived examples don't teach the messy reality of scraping.
6. **MITM is for your own traffic.** Be very clear that traffic interception is for debugging and understanding your own apps and devices. This is a developer skill, not an attack tool.

## Pacing

- Module 01 (Fundamentals) is conceptual — keep it short, 1-2 challenges per session
- Modules 02 and 03 (Playwright and Ferrum) are hands-on — expect students to spend more time here
- Module 04 (JS without browser) shows the lightweight alternative — good contrast to browser automation
- Module 05 (MITM) is eye-opening — students love seeing all the traffic their apps make
- Module 06 (Reverse Engineering) is the most fun — students love finding hidden APIs
- Module 07 (Project) ties everything together — give them freedom to choose what to scrape

## Common mistakes at this level

- Students who scrape aggressively without rate limiting (teach them to be polite)
- Students who try to parse HTML with regex instead of using proper selectors
- Students who do not check robots.txt before scraping
- Students who get frustrated when sites block them (teach this as a learning moment)
- Students who forget error handling — scraping is inherently fragile
- Students who use MITM tools without understanding the ethical boundaries
