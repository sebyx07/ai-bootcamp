# Teaching: Fix This Broken Page

## Context
The student has completed all 5 previous HTML challenges. They know boilerplate, text elements, links, images, forms, and semantic HTML. This challenge tests their debugging skills.

## The challenge
YOU create a broken HTML file first, then the student debugs it.

## Your approach

### Step 1: Create the broken file
Create a file called `broken.html` with at least 8-10 intentional errors. Include a mix of:
- Missing closing tags (e.g., `<h1>Title` without `</h1>`)
- Mismatched tags (e.g., `<h2>...</h3>`)
- Missing quotes on attributes (e.g., `<a href=https://example.com>`)
- Broken image (wrong `src` path or missing `alt`)
- `<label>` with wrong `for` attribute (doesn't match any `id`)
- Incorrectly nested elements (e.g., `<p><h2>Title</h2></p>`)
- Missing `<!DOCTYPE html>` declaration
- Using deprecated tags like `<center>` or `<font>`
- A link with no `href`
- A list without `<li>` items or with items outside the list

### Step 2: Present the challenge
Tell the student: "I've created a broken HTML page. Open `broken.html` in your browser — it won't look right. Your job is to find and fix every bug. I'll give you hints if you get stuck, but try to find them yourself first."

### Step 3: Guide the debugging
- Let the student find bugs on their own first
- If they're stuck, say: "Look at line X — does something look off?"
- After each fix, have them refresh the browser to see the change
- Do NOT fix bugs for them — only hint

### Step 4: Review
After all bugs are fixed, review what they found and explain any they missed.

## Prompting coaching
After they finish, note: "When you're debugging later, try prompts like `what's wrong with my HTML?` or `validate this HTML file`. Claude can spot issues fast."

## Quiz questions
- What happens in the browser when you forget a closing tag?
- How can you tell if tags are incorrectly nested?
- What is the fastest way to check if your HTML is valid?

## Hints (only if stuck)
1. Start from the top of the file — is the DOCTYPE there?
2. Check every opening tag to make sure it has a matching closing tag
3. Look at the browser output — where does it start looking wrong? The bug is usually just above that spot
