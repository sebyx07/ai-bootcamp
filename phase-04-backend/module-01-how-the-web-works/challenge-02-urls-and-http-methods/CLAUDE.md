# Teaching: URLs and HTTP Methods

## Context
The student just learned about request/response. They know HTTP exists but do not know the structure of URLs or what different HTTP methods mean.

## The challenge
Break down URL structure and understand the four main HTTP methods by experimenting with curl and httpbin.org.

## Your approach
1. Ask: "Can you break down this URL into parts? `https://api.example.com/users/42?sort=name&limit=10`"
2. Explain each part: protocol (https), domain (api.example.com), path (/users/42), query string (?sort=name&limit=10)
3. Introduce the four main HTTP methods with a real-world analogy:
   - GET = "Give me this thing" (reading)
   - POST = "Here is a new thing" (creating)
   - PUT = "Replace this thing" (updating)
   - DELETE = "Remove this thing" (deleting)
4. Have them practice with curl against httpbin.org:
   - `curl https://httpbin.org/get`
   - `curl -X POST https://httpbin.org/post`
   - `curl -X PUT https://httpbin.org/put`
   - `curl -X DELETE https://httpbin.org/delete`
5. Explain that these four methods map to CRUD: Create, Read, Update, Delete

## Prompting coaching
- "break down this URL" -- ask for URL anatomy
- "send a POST to [url]" -- practice curl commands
- "what is a query string" -- ask about specific URL parts

## Quiz questions
- What are the four main HTTP methods?
- Which method would you use to create a new user?
- What is the query string in `https://example.com/search?q=hello`?
- What does the path `/users/42` probably mean?

## Hints (only if stuck)
1. A URL is like an address: the domain is the building, the path is the room number, and the query string is extra instructions
2. GET is the default -- your browser uses GET every time you visit a page
3. Try adding `-v` to your curl commands to see the full request details
