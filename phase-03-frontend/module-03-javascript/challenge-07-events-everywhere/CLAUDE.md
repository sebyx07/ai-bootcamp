# Teaching: Events Everywhere

## Context
The student can handle click events from the previous challenge. Now they'll learn that clicks are just one of many events. This challenge expands their understanding of how JavaScript responds to user interaction. This should be built as an HTML page opened in the browser.

## The challenge
Build an interactive demo page with: a live text preview (updates as you type), a color picker that changes the page background, a keyboard listener that shows which key was pressed, and a form that displays submitted data without page reload.

## Your approach
1. Ask: "Clicks are great, but what other things does a user do on a web page?" — brainstorm: typing, hovering, scrolling, pressing keys, submitting forms
2. Show the `input` event: responds to every keystroke in a text field
   ```javascript
   input.addEventListener('input', (e) => {
     preview.textContent = e.target.value;
   });
   ```
3. Explain the event object (`e`): every event handler receives it, and `e.target` is the element that triggered the event
4. Show `keydown` event: `document.addEventListener('keydown', (e) => console.log(e.key));`
5. Show `mouseover` and `mouseout` for hover effects
6. Show `submit` event on forms with `e.preventDefault()` — explain why the page refreshes by default and how to stop it
7. Build each part one at a time, testing in the browser after each addition
8. Emphasize: "Events are how JavaScript knows the user did something"

## Prompting coaching
"Event-related prompts work well: `live preview as user types` or `prevent form from refreshing page`. Claude understands event patterns."

## Quiz questions
- What is the event object and what does `e.target` give you?
- What does `e.preventDefault()` do and when would you use it?
- What is the difference between `keydown` and `keyup`?

## Hints (only if stuck)
1. The `input` event fires on every character typed — great for live previews
2. `e.preventDefault()` stops the browser's default behavior (like form submission refreshing the page)
3. Every event listener callback receives an event object: `(e) => { console.log(e); }`
