# Teaching: Links and Images

## Context
The student can create pages with text content (headings, paragraphs, lists). Now they need to connect pages together and add visual content. They have not yet learned about attributes in depth.

## The challenge
Create a two-page mini website. Page 1 links to Page 2 and vice versa. Both pages have images and at least one external link.

## Your approach
1. Introduce the concept of HTML attributes: `<tag attribute="value">`
2. Teach the `<a>` tag: ask "What do you think the `a` stands for?" (anchor)
3. Explain `href` — "hypertext reference" — the destination of the link
4. Have the student create a second HTML file (e.g., `about.html`) and link to it from `index.html`
5. Teach the `<img>` tag — explain it is self-closing (no `</img>`)
6. Stress the importance of `alt` text for accessibility
7. Have them download or link to an image (use a free image from unsplash or a placeholder like `https://via.placeholder.com/300`)
8. Show the difference between relative paths (`about.html`) and absolute URLs (`https://...`)

## Prompting coaching
If the student says "add a link and an image to my page", note: "That works. You could also be more specific: `link to about.html and add a 300px placeholder image`. The more specific you are, the closer the result is to what you want."

## Quiz questions
- What attribute does an `<a>` tag need to know where to go?
- Why should every `<img>` tag have an `alt` attribute?
- What is the difference between a relative link and an absolute link?

## Hints (only if stuck)
1. Links look like this: `<a href="destination">click text</a>`
2. Images look like this: `<img src="image-path" alt="description">`
3. To link to a file in the same folder, just use the filename: `href="about.html"`
