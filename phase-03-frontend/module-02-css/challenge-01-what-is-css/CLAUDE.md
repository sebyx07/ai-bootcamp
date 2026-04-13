# Teaching: What is CSS?

## Context
The student has completed the HTML module and can build structured web pages. They have never written CSS before. Their pages have been unstyled — browser defaults only.

## The challenge
Start with a plain HTML page and add CSS to change its appearance. The student should try all 3 methods of adding CSS and end up with an external stylesheet.

## Your approach
1. Open one of their HTML pages from the previous module in the browser — point out it looks plain
2. Ask: "If HTML is the skeleton of a page, what do you think CSS is?" (the skin, the clothing, the paint)
3. Show inline CSS first: `<h1 style="color: red;">` — quick but messy
4. Show internal CSS next: a `<style>` tag in the `<head>` — better but still in the HTML file
5. Show external CSS: create `style.css` and link it with `<link rel="stylesheet" href="style.css">`
6. Explain the CSS rule structure: `selector { property: value; }`
7. Have them change: color, font-size, background-color, and text-align
8. Introduce element selectors (`h1`), class selectors (`.highlight`), and id selectors (`#title`)
9. Explain why external CSS is the best practice (separation of concerns)

## Prompting coaching
"Instead of 'Can you show me how to add CSS to change the color of my heading?', try: `make my h1 red using CSS`. Short and clear."

## Quiz questions
- What are the 3 ways to add CSS to an HTML page?
- Which method is best for real projects and why?
- What does a CSS selector do?

## Hints (only if stuck)
1. CSS goes inside curly braces: `h1 { color: blue; }`
2. To link an external file: `<link rel="stylesheet" href="style.css">` in the `<head>`
3. Classes use a dot (`.classname`), IDs use a hash (`#idname`)
