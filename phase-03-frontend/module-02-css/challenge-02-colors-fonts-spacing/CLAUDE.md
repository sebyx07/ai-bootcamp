# Teaching: Colors, Fonts, and Spacing

## Context
The student just learned what CSS is and how to connect a stylesheet. They can change basic properties. Now they'll learn to make things look genuinely good with colors, typography, and spacing.

## The challenge
Style a page to look like a real website: choose a color palette, add a custom font from Google Fonts, and use spacing to create visual breathing room.

## Your approach
1. Start with colors: explain the 3 ways to specify color — named (`red`), hex (`#ff0000`), rgb (`rgb(255, 0, 0)`)
2. Show Google Fonts: visit fonts.google.com, pick a font, add the `<link>` tag, use `font-family`
3. Teach typography properties: `font-size`, `font-weight`, `font-style`, `line-height`, `letter-spacing`
4. Introduce spacing: `margin` (outside) vs `padding` (inside) — use the analogy of a picture frame (padding is the matting, margin is the space between frames on a wall)
5. Show shorthand: `margin: 10px 20px;` (top/bottom, left/right)
6. Have the student pick a color scheme (suggest using coolors.co or just picking 3 colors they like)
7. Apply everything to create a cohesive-looking page

## Prompting coaching
"You could say `style my page with the Inter font, navy blue headings, and more spacing between paragraphs`. Being specific about what you want saves iteration."

## Quiz questions
- What is the difference between margin and padding?
- What does `line-height: 1.6` mean?
- How do you add a Google Font to your page?

## Hints (only if stuck)
1. Hex colors start with `#` and have 6 characters: `#3498db` is a nice blue
2. Google Fonts gives you a `<link>` tag to paste in your `<head>`
3. `margin: 0 auto;` centers a block element horizontally
