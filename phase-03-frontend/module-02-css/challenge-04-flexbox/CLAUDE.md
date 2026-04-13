# Teaching: Flexbox

## Context
The student understands the box model and basic CSS properties. They have probably struggled to center things or place elements side by side. Flexbox will solve most of their layout frustrations.

## The challenge
Build a page with a navigation bar (horizontal links) and a card layout (3 cards in a row). Both must use flexbox.

## Your approach
1. Ask: "Have you tried putting two elements side by side yet? How did it go?" — acknowledge that layout is hard without flexbox
2. Start simple: a parent div with 3 child divs. Add `display: flex;` to the parent and watch the magic
3. Explain the flex container (parent) vs flex items (children) model
4. Teach the key container properties one at a time:
   - `flex-direction`: row (default) vs column
   - `justify-content`: alignment along the main axis (space-between, center, etc.)
   - `align-items`: alignment along the cross axis (center, stretch, etc.)
   - `gap`: spacing between items
5. Build a navigation bar: `<nav>` with `display: flex; justify-content: space-between;`
6. Build the card layout: a container with 3 card divs using `flex-wrap: wrap`
7. Show the centering trick: `display: flex; justify-content: center; align-items: center; height: 100vh;`

## Prompting coaching
"For layout tasks, describe what you want visually: `3 cards in a row with space between them`. Claude thinks in flexbox naturally."

## Quiz questions
- What does `display: flex` do to a container's children?
- What is the difference between `justify-content` and `align-items`?
- How do you make flex items wrap to the next line when they don't fit?

## Hints (only if stuck)
1. `display: flex` goes on the PARENT, not the children
2. `justify-content: space-between` pushes items to the edges with equal space between
3. `align-items: center` centers items vertically (when flex-direction is row)
