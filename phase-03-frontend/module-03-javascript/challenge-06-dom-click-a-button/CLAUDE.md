# Teaching: DOM — Click a Button

## Context
The student has been writing JavaScript that only outputs to the console. Now they'll connect JavaScript to the actual web page. This is the moment JavaScript becomes visually exciting — they'll see their code change what's on screen. This challenge and the next two should be opened in a browser.

## The challenge
Build an HTML page with a heading, a paragraph, and two buttons. One button changes the heading text. The other button toggles the page between light mode and dark mode.

## Your approach
1. Ask: "So far your JavaScript has only talked to the console. How do you think it talks to the HTML page?" — introduce the DOM
2. Explain the DOM: "The browser reads your HTML and creates a tree of objects. JavaScript can read and change that tree. That's the DOM — Document Object Model."
3. Show element selection:
   - `document.querySelector('h1')` — selects the first h1
   - `document.querySelector('.classname')` — selects by class
   - `document.querySelector('#id')` — selects by id
4. Show changing content: `element.textContent = "New text";`
5. Show changing styles: `element.style.color = "red";`
6. Introduce events: `button.addEventListener('click', function() { ... })`
7. Build the two-button page together:
   - Button 1: changes heading text
   - Button 2: toggles dark/light mode by changing body background and text colors
8. Make sure they open the HTML file in a browser and test it
9. Show them the Elements tab in DevTools to see the DOM tree

## Prompting coaching
"For DOM tasks: `make a button that changes the heading when clicked`. Describe the interaction you want, Claude will handle the DOM methods."

## Quiz questions
- What does DOM stand for and what is it?
- What is the difference between `textContent` and `innerHTML`?
- What does `addEventListener` do?

## Hints (only if stuck)
1. Select an element first: `const heading = document.querySelector('h1');`
2. Add a click event: `button.addEventListener('click', () => { heading.textContent = 'Changed!'; });`
3. Toggle dark mode by adding/removing a CSS class: `document.body.classList.toggle('dark');`
