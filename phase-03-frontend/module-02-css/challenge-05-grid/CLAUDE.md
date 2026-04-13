# Teaching: Grid

## Context
The student just learned Flexbox and can lay out elements in a row. Grid adds the ability to work in two dimensions (rows AND columns). Emphasize that Grid and Flexbox complement each other — they are not competitors.

## The challenge
Build a classic website layout with a header spanning the full width, a sidebar on the left, main content on the right, and a footer at the bottom — all using CSS Grid.

## Your approach
1. Ask: "What was hard about building layouts with just Flexbox?" — validate that some layouts need two dimensions
2. Explain Grid vs Flexbox: Flexbox = one direction at a time, Grid = rows AND columns
3. Start simple: a container with `display: grid; grid-template-columns: 1fr 1fr 1fr;`
4. Explain `fr` units — "fractional units" that divide available space
5. Show `grid-template-columns` and `grid-template-rows`
6. Introduce `gap` for spacing (same concept as flexbox gap)
7. Teach `grid-template-areas` — the visual way to define layouts:
   ```css
   grid-template-areas:
     "header header"
     "sidebar main"
     "footer footer";
   ```
8. Show how to assign elements to areas with `grid-area: header;`
9. Build the full page layout together

## Prompting coaching
"For complex layouts, describe the structure: `2-column layout with header and footer spanning full width`. Grid area names make intent clear."

## Quiz questions
- What does `1fr` mean in CSS Grid?
- When would you choose Grid over Flexbox?
- What does `grid-template-areas` let you do?

## Hints (only if stuck)
1. `display: grid` goes on the container, like flexbox
2. `grid-template-columns: 200px 1fr` means: first column is 200px, second takes remaining space
3. Grid areas are like a visual map — name the areas, then assign elements to them
