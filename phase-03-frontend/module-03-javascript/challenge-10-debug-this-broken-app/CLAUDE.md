# Teaching: Debug This Broken App

## Context
The student has completed all 9 previous JavaScript challenges. They know variables, functions, arrays, objects, DOM manipulation, events, fetch, and async/await. This challenge tests their debugging skills by giving them a broken interactive app to fix.

## The challenge
YOU create a broken JavaScript app first, then the student debugs it in the browser.

## Your approach

### Step 1: Create the broken app
Create two files: `broken-app.html` and `broken-app.js`. The app should be a simple interactive page (like a task list or a quiz) with at least 8-10 intentional bugs. Include a mix of:

**Syntax / logic bugs:**
- Using `=` instead of `===` in a comparison
- Missing `return` statement in a function
- Off-by-one error in a loop (e.g., `i <= array.length` instead of `i < array.length`)
- Variable used before declaration (e.g., referencing a `const` before it's defined)
- Typo in a variable name (e.g., `documnet.querySelector`)

**DOM / event bugs:**
- `querySelector` using wrong selector (missing `.` for class or `#` for id)
- Event listener on an element that doesn't exist yet (script in head without defer)
- `textContent` used where `innerHTML` is needed (or vice versa)
- Forgetting `e.preventDefault()` on a form submit
- Trying to access `.value` on a non-input element

**Async bugs:**
- Forgetting `await` before a `fetch()` call
- Trying to use data outside the async function where it's not available yet

### Step 2: Present the challenge
Tell the student: "I've created a small app — but it's full of bugs. Open `broken-app.html` in your browser. Some things won't work at all, and some things will work wrong. Your mission: open the browser console, find every bug, and fix it. I'll give hints only if you're truly stuck."

### Step 3: Guide the debugging
- Have them open the browser console FIRST — errors will be visible there
- Let them find bugs on their own
- If stuck, say: "Check the console — what error do you see?" or "Look at line X in the JS file"
- After each fix, have them test in the browser
- Teach debugging techniques: `console.log()` values, reading error messages, checking the Elements tab

### Step 4: Review
Go through every bug they found. Explain any patterns: "This is a very common mistake. You'll see it in real code all the time."

## Prompting coaching
After they finish: "When debugging real code, try: `why am I getting 'cannot read property of null'?` or paste the error message directly. Claude is great at decoding error messages."

## Quiz questions
- What is the first thing you should check when JavaScript isn't working?
- What does "Cannot read property of undefined" usually mean?
- How does `console.log()` help you debug?

## Hints (only if stuck)
1. Open the browser console (F12 -> Console). Red text = errors. Read the error message and line number.
2. If something is `undefined`, check: did you spell the variable name right? Did you assign it?
3. If a DOM element is `null`, check: is the selector correct? Is the script running before the HTML loads?
