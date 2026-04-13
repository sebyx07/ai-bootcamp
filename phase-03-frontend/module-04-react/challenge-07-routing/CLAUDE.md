# Teaching: Routing

## Context
The student has a single-page React app. All content is on one page. Now they'll add navigation between different "pages" without the browser fully reloading. They understand components, state, and effects. This builds on the React project from previous challenges.

## The challenge
Add React Router to the existing project. Create Home, About, and Contact pages. Add a persistent navigation bar. Include a 404 page for unknown routes.

## Your approach
1. Ask: "Right now your app has one page. How would you add an 'About' page? Would you create a separate HTML file?" — explain that React handles it differently
2. Explain single-page apps: "The browser loads one HTML file. React Router swaps out components based on the URL — it feels like multiple pages but it's all one app."
3. Install React Router: `npm install react-router-dom`
4. Set up the router using **HashRouter** in `main.jsx` or `App.jsx`:
   ```jsx
   import { HashRouter, Routes, Route } from 'react-router-dom';
   ```
   - Explain: "HashRouter uses URLs like `/#/about` — the `#` tells the browser to handle routing on the client side. This works everywhere without special server config."
5. Create page components: `Home.jsx`, `About.jsx`, `Contact.jsx` (reuse the form from challenge 06)
6. Set up routes:
   ```jsx
   <HashRouter>
     <Routes>
       <Route path="/" element={<Home />} />
       <Route path="/about" element={<About />} />
       <Route path="/contact" element={<Contact />} />
       <Route path="*" element={<NotFound />} />
     </Routes>
   </HashRouter>
   ```
7. Create a navigation bar using `<Link to="/about">` instead of `<a href>`
8. Show `<NavLink>` for active link styling
9. Add a catch-all route with `path="*"` for the 404 page
10. Test navigation — show that the page doesn't reload
11. Mention BrowserRouter exists too (cleaner URLs like `/about`) but requires server config — HashRouter is simpler and works out of the box

## Prompting coaching
"For routing: `add React Router with Home, About, and Contact pages`. Listing the pages you want helps Claude set up all the routes at once."

## Quiz questions
- Why do React apps use `<Link>` instead of `<a>` for navigation?
- What does `path="*"` match?
- What is the difference between a multi-page website and a single-page app?

## Hints (only if stuck)
1. Install: `npm install react-router-dom`
2. Wrap your app in `<HashRouter>` and define routes with `<Routes>` and `<Route>`
3. Use `<Link to="/path">` for navigation — never use `<a href>` for internal links in React
