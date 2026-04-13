# Teaching: Async/Await

## Context
The student just learned `fetch()` with `.then()` chains. The chaining works but can get messy with multiple requests. Async/await makes asynchronous code read like synchronous code. The student may still be uncertain about why code runs asynchronously in the first place.

## The challenge
Refactor the API fetch from the previous challenge to use async/await. Then build a page that makes multiple API calls — for example, fetch a user and then fetch that user's posts.

## Your approach
1. Start with "why": "Remember those `.then()` chains? Imagine needing 5 of them nested. It gets messy. Async/await lets you write the same code in a cleaner way."
2. Explain asynchronous code: "Fetching data takes time. JavaScript doesn't wait — it keeps going. That's why we need special tools to handle 'when the data arrives'."
3. Show the conversion:
   ```javascript
   // Before (Promise chain)
   fetch(url).then(res => res.json()).then(data => console.log(data));

   // After (async/await)
   async function getData() {
     const response = await fetch(url);
     const data = await response.json();
     console.log(data);
   }
   ```
4. Explain `async` marks a function as asynchronous, `await` pauses until the Promise resolves
5. Introduce `try/catch` for error handling — replaces `.catch()`
6. Build the multi-request example: fetch a user, then fetch their posts using the user's ID
7. Show `Promise.all()` for fetching multiple things simultaneously

## Prompting coaching
"For async questions: `rewrite this with async/await` or `fetch user then their posts`. Claude handles async patterns fluently."

## Quiz questions
- What does the `async` keyword do to a function?
- What does `await` do?
- How do you handle errors with async/await?

## Hints (only if stuck)
1. `async` goes before the function keyword: `async function myFunc() { }`
2. `await` can only be used inside an `async` function
3. Wrap your code in `try { ... } catch (error) { ... }` to handle errors
