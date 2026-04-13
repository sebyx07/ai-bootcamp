# Teaching: useEffect

## Context
The student knows useState and can make interactive components. But what about code that should run when the component loads? Or when a specific value changes? useEffect handles "side effects" — anything outside of rendering UI. This builds on the React project from previous challenges.

## The challenge
Build a component that: (1) updates the document title to show the current count, (2) logs a message every time a state value changes, and (3) fetches a random joke from an API when the component loads.

## Your approach
1. Ask: "What if you wanted to fetch data as soon as a component appears on screen? Where would that code go?"
2. Explain side effects: "React components are for rendering UI. Anything else — fetching data, changing the page title, setting up a timer — is a 'side effect'. useEffect is where side effects live."
3. Show the basic pattern:
   ```jsx
   useEffect(() => {
     document.title = `Count: ${count}`;
   }, [count]);
   ```
4. Explain the dependency array:
   - `[]` — run only once, when the component first appears (like "on mount")
   - `[count]` — run when `count` changes
   - No array — run after every render (usually not what you want)
5. Build the document title updater: change the browser tab title as the counter changes
6. Build the API fetch: fetch a joke on mount using `useEffect` with `[]`
7. Show cleanup functions: `return () => { ... }` inside useEffect for timers or subscriptions
8. Connect to what they learned in the JS module: "Remember `fetch` and `async/await`? Same thing, just inside useEffect."

## Prompting coaching
"For effects: `fetch data on component mount` or `update title when count changes`. Describing WHEN something should happen maps perfectly to useEffect."

## Quiz questions
- What is a side effect in React?
- What does an empty dependency array `[]` mean?
- What happens if you forget the dependency array?

## Hints (only if stuck)
1. Import: `import { useEffect } from 'react';`
2. Run on mount: `useEffect(() => { /* code */ }, []);`
3. For async fetch inside useEffect, define an async function inside and call it immediately
