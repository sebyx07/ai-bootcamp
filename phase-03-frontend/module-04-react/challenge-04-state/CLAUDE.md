# Teaching: State

## Context
The student can create components and pass props. But props come from the parent — what about data that changes inside a component? State is the answer. This is one of the most important React concepts. This builds on the React project from previous challenges.

## The challenge
Build a counter component with increment, decrement, and reset buttons. Then build a toggle component that shows/hides content.

## Your approach
1. Ask: "If a user clicks a button to change a number, where does that number live? It's not a prop — the component owns it."
2. Introduce state: "State is data that belongs to a component and can change over time."
3. Show useState:
   ```jsx
   import { useState } from 'react';

   function Counter() {
     const [count, setCount] = useState(0);
     return (
       <div>
         <p>Count: {count}</p>
         <button onClick={() => setCount(count + 1)}>+1</button>
       </div>
     );
   }
   ```
4. Explain the hook: `useState(initialValue)` returns `[currentValue, setterFunction]`
5. Stress the rule: NEVER modify state directly (`count++` is wrong) — always use the setter
6. Explain: when state changes, React re-renders the component automatically
7. Add decrement and reset buttons to the counter
8. Build a toggle: `const [isVisible, setIsVisible] = useState(false);` with conditional rendering
9. Compare props vs state: props = external data passed in, state = internal data managed by the component

## Prompting coaching
"State prompts: `add a counter with useState` or `toggle dark mode with state`. Mentioning the hook name helps Claude use the right approach."

## Quiz questions
- What does `useState` return?
- Why can't you modify state directly (like `count = count + 1`)?
- What happens to the component when state changes?

## Hints (only if stuck)
1. Import useState: `import { useState } from 'react';`
2. Declare state: `const [value, setValue] = useState(initialValue);`
3. Update state: call `setValue(newValue)` — never change the variable directly
