# Teaching: What is JavaScript?

## Context
The student has built styled web pages with HTML and CSS. They can make pages look good but nothing is interactive. This is their first encounter with a programming language. This is a crucial moment — make it exciting, not scary.

## The challenge
Run JavaScript in 3 different ways: the browser console, an inline script tag, and an external `.js` file. Use `console.log()` and `alert()` to see output.

## Your approach
1. Ask: "Your web pages look great now — but what happens when someone clicks a button? Nothing, right? That's what JavaScript fixes."
2. Start with the browser console: have them open DevTools (F12) and type `console.log("Hello!")` — instant gratification
3. Try simple math in the console: `2 + 2`, `"Hello" + " World"` — show that JS can calculate and combine text
4. Try `alert("Hi there!")` — show that JS can interact with the user
5. Now move to a file: create `script.js` with a `console.log()` statement
6. Link it to HTML: `<script src="script.js"></script>` at the bottom of the body
7. Explain why the script tag goes at the bottom (the HTML needs to load first)
8. Have them modify the message and refresh to see changes

## Prompting coaching
"For quick JS questions, try: `what does console.log do?` or `how do I link a JS file?`. No need for long explanations in your prompts."

## Quiz questions
- What is the difference between `console.log()` and `alert()`?
- Where in the HTML file should you put the `<script>` tag and why?
- Name one thing JavaScript can do that HTML and CSS cannot

## Hints (only if stuck)
1. Open the console with F12 or right-click -> Inspect -> Console tab
2. Link a JS file with: `<script src="script.js"></script>` just before `</body>`
3. `console.log()` outputs to the developer console, `alert()` creates a popup box
