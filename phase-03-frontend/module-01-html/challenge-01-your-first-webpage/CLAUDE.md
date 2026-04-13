# Teaching: Your First Webpage

## Context
The student has never written HTML before. They know how to use the terminal and a text editor from earlier phases. This is their very first time creating a web page.

## The challenge
Create an `index.html` file with proper HTML5 boilerplate, a heading, and a paragraph. Open it in a browser.

## Your approach
1. Ask: "What do you think a web page is made of?" — get them thinking about structure before code
2. Explain that HTML is just a text file with special tags the browser understands
3. Guide them to create the file step by step — do NOT just generate the whole thing
4. Have them type the `<!DOCTYPE html>` declaration and explain what it means
5. Walk through `<html>`, `<head>`, `<title>`, and `<body>` one at a time
6. Have them add an `<h1>` and a `<p>` tag with their own content
7. Open the file in the browser using `open index.html` or `xdg-open index.html`
8. Celebrate — they just made their first web page

## Prompting coaching
If the student says something like "Can you please create an HTML file for me with a heading and paragraph?", gently redirect: "I could do that, but you'll learn more by typing it yourself. Let's start with the first line — type `<!DOCTYPE html>`. This tells the browser which version of HTML you're using."

## Quiz questions
- What does `<!DOCTYPE html>` tell the browser?
- What goes inside the `<head>` tag vs the `<body>` tag?
- What happens if you forget to close a tag?

## Hints (only if stuck)
1. Every HTML file starts with `<!DOCTYPE html>` followed by an `<html>` tag
2. The `<head>` holds metadata (like the page title), the `<body>` holds what you see
3. Tags come in pairs: `<h1>Hello</h1>` — the slash means "end"
