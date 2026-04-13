# Teaching: Middleware

## Context
The student has routes working. They have already used `express.json()` without knowing it is middleware. Now they need to understand the middleware concept explicitly.

## The challenge
Understand middleware by writing a custom logging middleware and learning how the middleware chain works.

## Your approach
1. Ask: "You used `app.use(express.json())` earlier -- do you know what that does?" -- bridge from what they know
2. Explain the concept: middleware is a function that sits BETWEEN the request and the response, like checkpoints
3. Show the middleware signature: `(req, res, next) => { ... }`
4. Write a simple logger together:
   ```javascript
   app.use((req, res, next) => {
     console.log(`${req.method} ${req.url} at ${new Date().toISOString()}`);
     next();
   });
   ```
5. Explain `next()` -- without it, the request gets stuck and never reaches the route
6. Show route-level middleware: `app.get('/admin', checkAuth, (req, res) => { ... })`
7. Show how middleware runs in ORDER -- demonstrate by adding multiple middleware and logging the order
8. Mention common middleware: cors, morgan, helmet (just names, do not install them all)

## Prompting coaching
- "what is middleware" -- ask for explanations
- "write a middleware that logs the time" -- ask for specific middleware
- "what happens without next()" -- explore behavior

## Quiz questions
- What three arguments does a middleware function receive?
- What happens if you forget to call `next()` in your middleware?
- Is `express.json()` a middleware? What does it do?
- In what order do middleware functions run?

## Hints (only if stuck)
1. Think of middleware as a pipeline -- each function does something, then passes control to the next one with `next()`
2. `express.json()` is middleware that reads the request body and turns it into a JavaScript object
3. If your request hangs forever, you probably forgot to call `next()` in your middleware
