# Teaching: What Is Web Scraping

## Context
The student has built frontend and backend projects. They know HTML, CSS, JavaScript, and how HTTP works. They have never programmatically extracted data from websites. This is the conceptual foundation before they write any scraping code.

## The challenge
The student will learn what web scraping is, understand why it exists, and explore real-world examples. This is a conceptual challenge — no code yet, just building a mental model.

## Your approach
1. Start by asking: "When you visit a website and see data — like product prices or news headlines — how would you get that data into a spreadsheet?" Let them brainstorm.
2. Explain web scraping in simple terms: it is writing a program that visits a webpage, reads the HTML, and pulls out the data you want. Like copy-paste, but automated.
3. Contrast scraping with APIs: "Remember when we built API endpoints in Phase 04? An API is like a front door — the site invites you in and hands you structured data. Scraping is like reading the bulletin board through the window — you get the info, but you have to parse it yourself."
4. Walk through real-world examples together:
   - **Price monitoring**: tracking Amazon prices over time to find deals
   - **Research**: collecting data from government sites or academic databases
   - **Data journalism**: gathering public records to investigate a story
   - **Job boards**: aggregating listings from multiple sites
   - **Real estate**: comparing listings across platforms
5. Ask them: "Can you think of a time you wished you could automatically collect data from a website?" Connect it to their interests.
6. Discuss when scraping is NOT the right tool: when an API exists, when data is behind a login you don't own, when it violates terms of service.
7. Send them to watch the video.

## Quiz questions
- What is the difference between scraping a website and using an API?
- Name 3 real-world uses of web scraping.
- If a website offers an API for its data, should you scrape it instead? Why or why not?

## Hints (only if stuck)
1. Think of scraping as "automated copy-paste" — your program reads the page the same way a browser does
2. APIs give you structured data (like JSON); scraping gives you raw HTML that you have to parse
3. Real uses are everywhere: price comparison sites, search engines, news aggregators — they all scrape
