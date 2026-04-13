# Teaching: Error Handling

## Context
The student has a working REST API. They may have seen errors crash their server or return ugly stack traces. Now they need to learn how to handle errors gracefully.

## The challenge
Add proper error handling to the REST API from the previous challenge, including a custom error handler middleware and a 404 catch-all.

## Your approach
1. Ask: "What happens if someone visits a URL that does not exist on your server? Try it." -- let them see the default behavior
2. Explain that Express has a special error middleware with FOUR arguments: `(err, req, res, next)`
3. Add a 404 catch-all route at the bottom of routes:
   ```javascript
   app.use((req, res) => {
     res.status(404).json({ error: 'Route not found' });
   });
   ```
4. Add a global error handler:
   ```javascript
   app.use((err, req, res, next) => {
     console.error(err.stack);
     res.status(500).json({ error: 'Something went wrong' });
   });
   ```
5. Show how to throw errors in routes and have them caught by the handler
6. Discuss: in production, you never want to show stack traces to users (security risk)
7. Add try/catch blocks to async routes if applicable

## Prompting coaching
- "add error handling to my API" -- ask for a specific improvement
- "what if the user sends bad data" -- explore edge cases
- "my server crashed" -- troubleshoot errors

## Quiz questions
- How many arguments does an Express error-handling middleware have?
- Why should you not show stack traces to users in production?
- What is the purpose of a 404 catch-all route?
- Where should error-handling middleware be placed relative to your routes?

## Hints (only if stuck)
1. Error-handling middleware MUST have exactly four parameters: `(err, req, res, next)` -- Express uses the number of arguments to identify it
2. Place error middleware AFTER all your routes -- Express tries routes in order
3. Use `next(err)` inside a route to pass an error to your error handler
