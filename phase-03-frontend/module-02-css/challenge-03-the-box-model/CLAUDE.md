# Teaching: The Box Model

## Context
The student has worked with colors, fonts, and basic spacing. They have used margin and padding but may not fully understand how element sizing works. The box model is one of the most important CSS concepts.

## The challenge
Create a visual demonstration of the box model. Build a page with several boxes that clearly show content, padding, border, and margin using distinct colors and sizes.

## Your approach
1. Ask: "When you set a div to be 200px wide and add 20px of padding, how wide do you think it actually is?" (most beginners guess 200px — the answer is 240px with the default box model)
2. Draw the box model with code: create a colored div with visible padding (different background), a thick border, and margin
3. Explain the 4 layers from inside out: content -> padding -> border -> margin
4. Show the problem: `width: 200px` + `padding: 20px` + `border: 5px` = 250px total
5. Introduce `box-sizing: border-box` — makes width include padding and border
6. Have them add `* { box-sizing: border-box; }` as a global reset
7. Show them how to use browser DevTools (right-click -> Inspect -> see the box model diagram)
8. Create a few different boxes to practice

## Prompting coaching
"When debugging layout issues, try: `why is my div wider than 200px?` — Claude can explain box model math instantly."

## Quiz questions
- What are the 4 parts of the CSS box model, from inside to outside?
- What does `box-sizing: border-box` change?
- If an element has `width: 300px`, `padding: 20px`, and `border: 5px`, what is its total width with default box-sizing?

## Hints (only if stuck)
1. Background color fills the content AND padding area — use a different background on a parent to see padding
2. `border: 3px solid black;` makes the border visible
3. Open DevTools with F12 or right-click -> Inspect, then look at the Computed tab for the box model diagram
