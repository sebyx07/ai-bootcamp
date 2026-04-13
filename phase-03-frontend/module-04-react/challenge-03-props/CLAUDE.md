# Teaching: Props

## Context
The student can create components but they're static — same content every time. Props let them pass data into components, making them dynamic. This is a fundamental React concept. This builds on the React project from previous challenges.

## The challenge
Use the Card component from the previous challenge and make it dynamic with props. Then create an array of data and map over it to render multiple cards.

## Your approach
1. Ask: "Your Card component shows the same content every time. What if you wanted 5 cards with different titles and descriptions?"
2. Show how props work:
   ```jsx
   // Parent passes data
   <Card title="Learn React" description="Build awesome UIs" />

   // Child receives it
   function Card({ title, description }) {
     return (
       <div className="card">
         <h2>{title}</h2>
         <p>{description}</p>
       </div>
     );
   }
   ```
3. Explain props are like function arguments — the parent passes them, the child uses them
4. Show destructuring: `function Card({ title, description })` vs `function Card(props)` then `props.title`
5. Emphasize: props flow ONE direction — parent to child (not the other way)
6. Create an array of data objects in App.jsx and use `.map()` to render a Card for each
7. Explain the `key` prop: React needs it to track list items — use a unique id
8. Show passing different prop types: strings, numbers, booleans, and even functions

## Prompting coaching
"Try: `make Card accept title and description props` or `render a list of cards from an array`. Component + data = clear prompt."

## Quiz questions
- What are props in React?
- Why do props only flow from parent to child?
- Why does React need a `key` prop when rendering lists?

## Hints (only if stuck)
1. Pass props like HTML attributes: `<Card title="Hello" />`
2. Receive props by destructuring the parameter: `function Card({ title }) { ... }`
3. When mapping: `data.map(item => <Card key={item.id} title={item.title} />)`
