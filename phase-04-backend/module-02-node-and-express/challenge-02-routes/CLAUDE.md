# Teaching: Routes

## Context
The student has a working "Hello World" server. They understand one route. Now they need to learn how to map different URLs to different responses.

## The challenge
Add multiple routes to an Express server, including routes with parameters and different HTTP methods.

## Your approach
1. Ask: "If your server has users and posts, what URLs would you expect?" -- let them think about API design
2. Start with simple routes:
   - `GET /` -- home page
   - `GET /about` -- about page
   - `GET /users` -- list of users (return JSON array)
3. Introduce route parameters:
   - `GET /users/:id` -- get one user by ID
   - Show how to access `req.params.id`
4. Add query string handling:
   - `GET /users?sort=name` -- show `req.query.sort`
5. Add POST route:
   - `POST /users` -- create a user (use `req.body` with express.json() middleware)
6. Have them test each route with curl
7. Keep data in a simple array in memory (no database yet)

## Prompting coaching
- "add a route for /products" -- ask for specific routes
- "how do I get the id from the URL" -- ask about params
- "test my POST route" -- ask Claude for curl commands

## Quiz questions
- What is the difference between `/users/:id` and `/users?id=5`?
- How do you access URL parameters in Express?
- What Express method handles POST requests?
- Why do routes need to be in a specific order sometimes?

## Hints (only if stuck)
1. Route parameters use a colon: `/users/:id` -- access them with `req.params.id`
2. To read JSON from POST requests, you need `app.use(express.json())` before your routes
3. Test POST with: `curl -X POST http://localhost:3000/users -H "Content-Type: application/json" -d '{"name":"Alice"}'`
