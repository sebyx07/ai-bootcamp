# Teaching: Use curl and Postman

## Context
The student has used curl briefly in earlier challenges. They understand HTTP methods and JSON. Now they need to become comfortable using these tools to test APIs -- a daily skill for backend developers.

## The challenge
Use curl to interact with a real public API (JSONPlaceholder). Send different types of requests, include JSON bodies, and read the responses.

## Your approach
1. Start with a simple GET: `curl https://jsonplaceholder.typicode.com/posts/1`
2. Show how to format output: `curl -s https://jsonplaceholder.typicode.com/posts/1 | python3 -m json.tool`
3. Send a POST with JSON body:
   ```
   curl -X POST https://jsonplaceholder.typicode.com/posts \
     -H "Content-Type: application/json" \
     -d '{"title": "My Post", "body": "Hello world", "userId": 1}'
   ```
4. Teach the key curl flags: `-X` (method), `-H` (header), `-d` (data), `-v` (verbose), `-s` (silent)
5. Have them explore: list all posts, get one post, create a post, update a post, delete a post
6. Explain that Postman does the same thing but with a graphical interface -- mention it as a tool they can explore on their own
7. Challenge: "Use curl to get all posts by user 1" (hint: query parameter)

## Prompting coaching
- "curl GET posts" -- short requests for specific curl commands
- "add a header to my request" -- ask for specific curl flags
- "what does -d do in curl" -- ask about specific flags

## Quiz questions
- What curl flag sets the HTTP method?
- How do you send a JSON body with curl?
- What header tells the server you are sending JSON?
- What is the difference between curl and Postman?

## Hints (only if stuck)
1. The `-H "Content-Type: application/json"` header tells the server your data is JSON
2. Use `-d` followed by your JSON string to send data in the request body
3. Try `curl https://jsonplaceholder.typicode.com/posts?userId=1` to filter posts by user
