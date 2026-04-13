# Teaching: SCSS Basics

## Context
The student is comfortable with CSS. They have written enough CSS to feel the pain points: repeating colors, long selectors, no variables. SCSS solves these problems. They have Node.js installed from Phase 02.

## The challenge
Convert one of their existing CSS files to SCSS. Add variables for colors and fonts, use nesting for cleaner selectors, and create a mixin for a reusable pattern (like a button style or media query).

## Your approach
1. Ask: "When writing CSS, was there anything that felt repetitive or annoying?" — validate the problems SCSS solves
2. Explain what SCSS is: "A superset of CSS — all valid CSS is valid SCSS, but SCSS adds extra features"
3. Install the Sass compiler: `npm install -g sass` (or use npx)
4. Create a `.scss` file and show it must be compiled: `sass style.scss style.css`
5. Teach variables: `$primary-color: #3498db;` then use: `color: $primary-color;`
6. Teach nesting:
   ```scss
   .nav {
     ul {
       list-style: none;
       li {
         display: inline;
       }
     }
   }
   ```
7. Teach mixins: reusable blocks of styles with parameters
8. Show the `--watch` flag: `sass --watch style.scss style.css` to auto-compile on save
9. Mention partials (`_variables.scss`) for organizing larger projects

## Prompting coaching
"You can ask Claude to convert CSS to SCSS: `convert my style.css to SCSS with variables for colors`. It handles the mechanical work while you learn the patterns."

## Quiz questions
- What is the difference between CSS and SCSS?
- How do you create and use a variable in SCSS?
- Why can't browsers read SCSS files directly?

## Hints (only if stuck)
1. SCSS variables start with `$`: `$font-size: 16px;`
2. Nesting follows the HTML structure — if `li` is inside `ul`, nest the `li` styles inside `ul` styles
3. A mixin is like a function: `@mixin button($bg) { background: $bg; padding: 10px; }` used with `@include button(blue);`
