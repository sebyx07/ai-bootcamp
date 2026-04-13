# Teaching: Semantic HTML

## Context
The student can build complete HTML pages with text, links, images, and forms. They have probably been using `<div>` tags for structure. Now they'll learn that HTML has tags with built-in meaning.

## The challenge
Rebuild or restructure one of their earlier pages using semantic HTML tags. The page should represent a blog or news article with a proper header, navigation, main content area, sidebar, and footer.

## Your approach
1. Ask: "Do you know what 'semantic' means?" — it means the tag describes its purpose
2. Show the difference: `<div class="header">` vs `<header>` — same visual result, but one has meaning
3. Explain why this matters: screen readers for blind users, search engines, other developers reading your code
4. Walk through the main semantic tags:
   - `<header>` — top of the page or section
   - `<nav>` — navigation links
   - `<main>` — the primary content
   - `<section>` — a thematic group of content
   - `<article>` — self-contained content (like a blog post)
   - `<aside>` — sidebar or tangential content
   - `<footer>` — bottom of the page or section
5. Have them restructure their page using these tags
6. Ask: "If a screen reader announced each section, would the structure make sense?"

## Prompting coaching
Show them that short prompts work: "Instead of 'Can you help me convert my div-based layout to use semantic HTML elements?', just say `convert divs to semantic HTML`."

## Quiz questions
- What is the difference between `<section>` and `<article>`?
- Why should you use `<nav>` instead of `<div class="nav">`?
- Name two groups of people who benefit from semantic HTML

## Hints (only if stuck)
1. Think of your page like a newspaper: header at top, navigation to get around, main story in the middle, footer at the bottom
2. `<article>` is for content that could stand on its own (like a blog post or news story)
3. You can nest semantic tags: a `<section>` can go inside `<main>`, and `<article>` can go inside `<section>`
