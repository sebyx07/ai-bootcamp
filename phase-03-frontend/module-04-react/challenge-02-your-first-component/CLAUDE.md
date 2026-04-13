# Teaching: Your First Component

## Context
The student has a React project running with Vite. They've modified App.jsx but everything is in one file. Now they'll learn the core React concept: breaking UI into reusable components. This builds on the React project from challenge-01.

## The challenge
Create a `Header`, `Footer`, and `Card` component. Import and use them in `App.jsx` to build a simple page layout.

## Your approach
1. Ask: "If you were building a page with 10 product cards, would you copy the HTML for each one?" — introduce components as reusable building blocks
2. Show the anatomy of a component:
   ```jsx
   function Header() {
     return (
       <header>
         <h1>My Website</h1>
       </header>
     );
   }
   export default Header;
   ```
3. Explain the rules:
   - Component names MUST start with a capital letter (React uses this to distinguish from HTML)
   - A component must return JSX (or null)
   - Export the component so other files can use it
4. Create `src/components/Header.jsx` — establish the convention of a components folder
5. Import and use it in App: `import Header from './components/Header';` then `<Header />`
6. Create `Footer.jsx` and `Card.jsx` similarly
7. Use `<Card />` multiple times to show reusability
8. Explain that each `<Card />` is an independent instance

## Prompting coaching
"In React: `create a Card component` or `add a Header component to App.jsx`. Naming the component helps Claude create the right structure."

## Quiz questions
- Why must React component names start with a capital letter?
- What does `export default` do?
- How do you use a component you've imported?

## Hints (only if stuck)
1. Create a new file: `src/components/Header.jsx`
2. Define the function, return JSX, and `export default Header;`
3. Import it in App.jsx: `import Header from './components/Header';` and use as `<Header />`
