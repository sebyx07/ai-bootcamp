# Teaching: Make This Ugly Page Nice

## Context
The student has completed all 7 previous CSS challenges. They know selectors, colors, fonts, the box model, flexbox, grid, responsive design, and SCSS. This is a creative capstone challenge.

## The challenge
YOU create an intentionally ugly but functional HTML page. The student redesigns it using CSS.

## Your approach

### Step 1: Create the ugly page
Create a file called `ugly.html` with embedded ugly styles. The page should be functional (real content, working structure) but visually terrible:
- Use Comic Sans or Papyrus fonts
- Clashing neon colors (lime green background, magenta text, yellow borders)
- No spacing — everything crammed together
- Inconsistent font sizes (some text huge, some tiny)
- No layout — everything stacked in a single column with no max-width
- Borders around everything (thick, dotted, in random colors)
- Images that are either way too big or way too small
- The page should have: a header, a navigation bar, a main content area with at least 2 sections, some cards or list items, and a footer

### Step 2: Present the challenge
Tell the student: "I've created a perfectly functional webpage — the HTML is fine. But it looks absolutely terrible. Your mission: make it beautiful using only CSS. Don't change the HTML at all (or as little as possible). Create a new `style.css` file and transform this page."

### Step 3: Guide the redesign
- Let the student drive the design decisions
- Ask: "What's the first thing you'd fix?" — let them prioritize
- If they're stuck on design choices, suggest looking at a site they admire for inspiration
- Encourage them to use what they've learned: flexbox for the nav, grid for the layout, media queries for responsiveness
- Do NOT write the CSS for them — offer guidance like "have you considered using flexbox for those cards?"

### Step 4: Review and celebrate
When they're done, compare before and after. Point out specific things they did well.

## Prompting coaching
"When working on design, try prompts like `suggest a color palette for a modern blog` or `what font pairs well with Inter?`. Use Claude for inspiration, not implementation."

## Quiz questions
- What CSS properties had the biggest visual impact on the redesign?
- How did you decide on your color palette?
- What would you do differently if you started over?

## Hints (only if stuck)
1. Start with the basics: reset the font to something clean (Inter, system-ui), set a reasonable max-width on the body, add padding
2. Pick 2-3 colors maximum. Use one for accents, one for text, one for backgrounds
3. Use flexbox for the navigation, grid for the card layout, and a media query at 768px for mobile
