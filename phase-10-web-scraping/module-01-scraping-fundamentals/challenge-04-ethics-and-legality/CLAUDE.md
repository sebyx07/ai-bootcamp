# Teaching: Ethics and Legality

## Context
The student now understands what scraping is, how to find elements in HTML, and how HTTP requests work. Before they write any scraping code, they need to understand the rules. This is not optional — irresponsible scraping can get IP addresses banned, violate laws, or take down small websites. This challenge builds good habits from the start.

## The challenge
The student will explore robots.txt files on real websites, learn about rate limiting and Terms of Service, and develop a personal checklist for responsible scraping.

## Your approach
1. Start with a question: "If you built a website and someone's script hit it 1000 times per second, how would that affect your server?" Let them think about it from the site owner's perspective.
2. Introduce robots.txt: "Most websites have a file called robots.txt that tells scrapers what they are and are not allowed to access. It is like a sign on the door."
3. Hands-on: fetch robots.txt for 3 popular sites using curl:
   - `curl https://www.google.com/robots.txt`
   - `curl https://www.amazon.com/robots.txt`
   - `curl https://en.wikipedia.org/robots.txt`
4. Walk through the format together: User-agent, Disallow, Allow, Crawl-delay. Ask them to interpret what they see.
5. Discuss the key principles of polite scraping:
   - **Respect robots.txt**: if it says Disallow, do not scrape that path
   - **Rate limiting**: add delays between requests (1-2 seconds minimum) so you do not overwhelm the server
   - **Identify yourself**: use a descriptive User-Agent so the site owner knows who you are
   - **Check Terms of Service**: some sites explicitly forbid scraping in their ToS
   - **Cache responses**: do not re-fetch pages you already have
   - **Scrape during off-peak hours**: reduce impact on the server
6. Briefly cover the legal landscape: robots.txt is not legally binding but is ethically important. The legal situation varies by country. The key court cases (hiQ vs LinkedIn) show it is a gray area. Rule of thumb: public data is generally fair game, but respect the site's wishes.
7. Have them create a "scraper checklist" they can reference later — a simple list of things to check before scraping any site.

## Quiz questions
- What is robots.txt and what does it tell scrapers?
- Why should you add delays between requests when scraping?
- If a website's Terms of Service say "no scraping," what should you do?
- What does "Crawl-delay: 10" mean in a robots.txt file?

## Hints (only if stuck)
1. robots.txt lives at the root of every website — just add /robots.txt to any domain to see it
2. Without delays, your scraper could send hundreds of requests per second — that is basically a denial-of-service attack on a small server
3. "Disallow: /private/" means scrapers should not access any URL starting with /private/
