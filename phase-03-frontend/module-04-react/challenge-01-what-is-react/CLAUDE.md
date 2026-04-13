# Teaching: What is React?

## Context
The student has completed the HTML, CSS, and JavaScript modules. They can build interactive pages with vanilla JS, manipulate the DOM, and fetch data. React will feel like a big leap — there's a build tool, a different file format (JSX), and a new mental model (components). Go slow and connect to what they already know.

## The challenge
Set up a React project with Vite, understand the file structure, and modify the default page to show custom content.

## Your approach
1. Ask: "In your JavaScript challenges, what was annoying about updating the DOM manually?" — validate the problem React solves
2. Explain React in one sentence: "React lets you describe what the page should look like, and it handles updating the DOM for you."
3. Explain components: "Instead of one big HTML file, you break the page into small, reusable pieces called components."
4. Set up the project:
   ```bash
   npm create vite@latest my-react-app -- --template react
   cd my-react-app
   npm install
   npm run dev
   ```
5. Open the running app in the browser — show the default Vite+React page
6. Walk through the file structure: `src/App.jsx`, `src/main.jsx`, `index.html`
7. Explain JSX: "It looks like HTML but it's actually JavaScript. That's why it's in a `.jsx` file."
8. Have them modify `App.jsx` to show their own heading and paragraph
9. Show that the browser auto-updates when they save (hot module replacement)

## Prompting coaching
"In React projects, try: `add a heading to App.jsx` or `explain the React file structure`. React prompts work best when you reference the specific file."

## Quiz questions
- What problem does React solve that plain JavaScript doesn't?
- What is JSX?
- What is a component?

## Hints (only if stuck)
1. Use Vite to create the project: `npm create vite@latest my-react-app -- --template react`
2. The main component is in `src/App.jsx` — edit it like HTML (but it's JSX)
3. JSX requires one parent element — wrap everything in a `<div>` or `<>...</>` (fragment)
