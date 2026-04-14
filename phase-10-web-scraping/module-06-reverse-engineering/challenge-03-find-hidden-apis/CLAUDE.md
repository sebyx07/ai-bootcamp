# Teaching: Find Hidden APIs

## Context
The student knows how to use the Network tab. Now they need to apply that skill to discover APIs that sites use internally. Many websites have undocumented APIs powering search, pagination, filtering, and infinite scroll — these are goldmines for data extraction.

## The challenge
Visit real websites, interact with them (search, scroll, paginate, filter), and find at least 2 hidden API endpoints by watching the Network tab. Document what each endpoint does and what data it returns.

## Your approach
1. Explain the concept: most modern websites are SPAs or use AJAX — they load data from APIs without full page reloads. These APIs aren't documented publicly but they're right there in the Network tab
2. Have the student watch the video (or skip if they just watched it in the previous challenge)
3. Guide the student through finding hidden APIs:
   - Pick a site together (e.g., a news site, Reddit, GitHub, a weather site)
   - Open Network tab, filter XHR/Fetch
   - Perform actions: type in a search box, scroll down, click "load more," change a filter
   - Watch for new requests appearing — these are the hidden APIs
   - Click each one, look at the URL pattern and response data
4. Have the student find APIs on a second site on their own
5. Document findings together: endpoint URL, HTTP method, what triggers it, what data comes back
6. Discuss patterns: many APIs use query parameters like `?q=search_term&page=2` — these are easy to manipulate

## Quiz questions
- Why do most modern websites have hidden APIs even though they don't document them publicly?
- If you see `?page=1` in an API URL, what could you change to get more data?
- What's the difference between a public API (like OpenWeatherMap) and a hidden API you discover in the Network tab?

## Hints (only if stuck)
1. Try sites that have search functionality — type something and watch the Network tab
2. Sites with infinite scroll or "Load More" buttons almost always use API calls
3. Look at the response — if it's JSON, you've found an API endpoint
