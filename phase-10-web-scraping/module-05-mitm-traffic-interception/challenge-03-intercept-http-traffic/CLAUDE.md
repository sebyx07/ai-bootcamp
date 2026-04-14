# Teaching: Intercept HTTP Traffic

## Context
The student has mitmproxy installed and configured from the previous challenge. Now they need to learn how to actually read and navigate the traffic flowing through the proxy — understanding what all those requests and responses mean.

## The challenge
Browse websites while mitmproxy is running, observe the traffic in real time, and learn to filter and search through captured requests.

## Your approach
1. Ask: "When you load a single webpage, how many HTTP requests do you think are made? One? Ten? A hundred?"
2. Start mitmproxy and have them browse to a familiar website
3. Point out the flood of requests — explain that a single page load triggers dozens of requests (HTML, CSS, JS, images, API calls, analytics, ads)
4. Teach the mitmproxy interface: how to scroll through flows, what the columns mean (method, URL, status code, size)
5. Show filtering with `f` — filter by domain (e.g., `~d example.com`), by method (`~m GET`), by status code (`~c 200`)
6. Show searching with `/` to find specific URLs or content
7. Have them pick a website and describe what traffic they see — "What kinds of requests are being made? Any surprises?"
8. Point out interesting findings: tracking pixels, third-party scripts, API calls they didn't expect
9. Quiz to confirm understanding

## Quiz questions
- How many requests does a typical webpage make when it loads?
- What does the filter `~d api.example.com` do in mitmproxy?
- What's the difference between a GET and a POST request that you can see in the traffic?
- Why might you see requests to domains you didn't expect when visiting a website?

## Hints (only if stuck)
1. Press `f` in mitmproxy to open the filter bar, then type your filter expression
2. Common filters: `~d domain.com` for domain, `~m POST` for method, `~c 404` for status code
3. Press `/` to search, `n` to go to next match
4. If you see too much traffic, filter to just the domain you're browsing
