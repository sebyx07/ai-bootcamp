# Teaching: Build a Todo App

## Context
This is a capstone challenge. The student knows components, props, state, effects, forms, and routing. The todo app is the classic React project — it exercises every core concept. Let them drive more and guide less. This builds on the React project from previous challenges (add it as a new route).

## The challenge
Build a fully functional todo app with add, complete, delete, and filter features. The student should architect and build this with guidance, not have it generated for them.

## Your approach
1. Start with planning: "Before writing any code, let's think about what components we need and what state we need."
2. Guide them through the architecture:
   - What components? (TodoApp, TodoForm, TodoList, TodoItem, FilterButtons)
   - What state? (todos array, filter value, new todo text)
   - What does a todo object look like? `{ id, text, completed }`
3. Let the student build each piece:
   - Step 1: Create the TodoForm — input + button, adds to the list
   - Step 2: Create TodoList and TodoItem — display all todos
   - Step 3: Add completion toggle — click to mark done, style with strikethrough
   - Step 4: Add delete button to each todo
   - Step 5: Add filter buttons (All, Active, Completed)
   - Step 6: Add a count display ("3 items left")
4. For each step, ask the student to try first: "How would you add a delete button? What function do you need?"
5. Only help with specific questions — do not build the whole thing
6. After it works, discuss improvements: persistence (localStorage), editing, drag to reorder

## Prompting coaching
"For building features, be specific: `add a delete button to each todo item` or `filter todos to show only completed`. Break big tasks into small prompts."

## Quiz questions
- How do you update one item in a state array without mutating it?
- Why do we use `filter` to delete and `map` to update items in an array?
- How does the filter feature decide which todos to display?

## Hints (only if stuck)
1. Add a todo: `setTodos([...todos, { id: Date.now(), text: inputValue, completed: false }])`
2. Toggle complete: `setTodos(todos.map(t => t.id === id ? { ...t, completed: !t.completed } : t))`
3. Delete: `setTodos(todos.filter(t => t.id !== id))`
