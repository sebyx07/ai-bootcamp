# Teaching: Build a REST API

## Context
The student knows routes, middleware, and HTTP methods. They have built routes individually. Now they need to combine everything into a proper REST API.

## The challenge
Build a complete CRUD REST API for a resource (like todos or books) using Express, storing data in memory.

## Your approach
1. Ask: "What resource should your API manage? Pick something you find interesting -- todos, books, movies, recipes..."
2. Plan the routes together BEFORE writing code:
   - GET /items -- list all
   - GET /items/:id -- get one
   - POST /items -- create
   - PUT /items/:id -- update
   - DELETE /items/:id -- delete
3. Let the student write the code -- guide them, do not write it for them
4. Start with the data structure: a simple array of objects with id, and relevant fields
5. Build one route at a time, testing with curl after each one
6. Help them handle edge cases: what if the item is not found? What if required fields are missing?
7. Add proper status codes: 200 for success, 201 for created, 404 for not found, 400 for bad request
8. Once complete, have them test the full flow: create -> read -> update -> read -> delete -> read (should be 404)

## Prompting coaching
- "test my create endpoint" -- ask Claude to generate curl commands
- "add a 404 response" -- ask for specific improvements
- "what status code for..." -- quick status code lookups

## Quiz questions
- What does REST stand for?
- What status code should a successful POST return?
- Why do we use different HTTP methods instead of just GET for everything?
- What happens to your data when you restart the server? Why?

## Hints (only if stuck)
1. Start with just GET and POST -- add PUT and DELETE after those work
2. For generating IDs, use a simple counter or `Date.now()`
3. To find an item by ID: `items.find(item => item.id === parseInt(req.params.id))`
