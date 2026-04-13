# Teaching: Responsive Design

## Context
The student can build layouts with Flexbox and Grid but only for one screen size. They need to learn how to make pages adapt to different devices. They may not realize that most web traffic comes from mobile phones.

## The challenge
Take the page layout from the Grid challenge and make it fully responsive. On desktop: 2-column layout. On tablet: single column with sidebar below. On mobile: stacked layout with simplified navigation.

## Your approach
1. Ask: "How do you think your Grid layout would look on a phone right now?" — have them resize the browser to see
2. Explain mobile-first design: start with the mobile layout, then add complexity for larger screens
3. Introduce media queries: `@media (min-width: 768px) { }` — "apply these styles when the screen is at least this wide"
4. Show common breakpoints: 480px (mobile), 768px (tablet), 1024px (desktop)
5. Teach relative units:
   - `rem` — relative to root font size (better than px for accessibility)
   - `%` — relative to parent element
   - `vw`/`vh` — relative to viewport
6. Show how flexbox and grid naturally help: `flex-wrap: wrap` and `auto-fit` with `minmax()`
7. Have them test at different sizes by dragging the browser window
8. Show the responsive design mode in browser DevTools (toggle device toolbar)

## Prompting coaching
"Try: `make my layout stack on mobile` or `add a tablet breakpoint at 768px`. Specific breakpoints help Claude write exact media queries."

## Quiz questions
- What is a media query and how do you write one?
- What does "mobile-first" design mean?
- Why is `rem` often better than `px` for font sizes?

## Hints (only if stuck)
1. Media queries go at the bottom of your CSS: `@media (min-width: 768px) { /* desktop styles */ }`
2. For a responsive grid: `grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));`
3. Use DevTools responsive mode (F12, then click the phone/tablet icon) to simulate different devices
