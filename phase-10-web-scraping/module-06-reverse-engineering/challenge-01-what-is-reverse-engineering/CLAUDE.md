# Teaching: What Is Reverse Engineering?

## Context
The student has learned scraping fundamentals, Playwright, and Ferrum. They know how to extract data from HTML. Now they need to understand that many modern sites load data via APIs — and you can discover those APIs by watching what the browser does behind the scenes.

## The challenge
This is a conceptual challenge. The student will learn the mindset of reverse engineering: observing how websites work from the outside, finding patterns in network requests, and discovering undocumented APIs that power the pages they see.

## Your approach
1. Give a short overview: reverse engineering means figuring out how something works by observing it, not by reading its source code
2. Have the student watch the video
3. After the video, discuss real-world examples together:
   - When you search on a shopping site, there's an API call fetching results
   - When you scroll and more items load, that's an API call too
   - When you filter or sort, the browser is hitting an endpoint with parameters
4. Walk through the concept: instead of scraping the rendered HTML, you can often call the same API the site uses and get clean JSON back
5. Discuss why this matters: APIs return structured data (JSON), are faster to work with, and are more reliable than parsing HTML
6. Briefly touch on ethics: reverse engineering for learning and personal use is generally fine, but respect terms of service and rate limits

## Quiz questions
- What does reverse engineering mean in a web context?
- Why might calling a site's hidden API be better than scraping its HTML?
- What tool in the browser helps you see what API calls a website makes?

## Hints (only if stuck)
1. Think about what happens when you type in a search box on Amazon or Google — the page updates without fully reloading
2. The browser's Network tab shows every request the page makes, including API calls
3. Modern sites are often just a frontend that talks to a backend API — if you find that API, you can talk to it directly
