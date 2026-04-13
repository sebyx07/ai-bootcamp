# Teaching: Forms in React

## Context
The student built forms in the HTML module using plain HTML. In React, forms work differently — inputs are controlled by state. The student knows useState and useEffect. This builds on the React project from previous challenges.

## The challenge
Build a contact form with name, email, and message fields. Each input is controlled by state. On submit, display the submitted information below the form and clear the inputs.

## Your approach
1. Ask: "Remember HTML forms? In React, we do something different — every input is connected to state. Can you guess why?"
2. Explain controlled components: the input's value comes from state, and typing updates state
3. Show the pattern:
   ```jsx
   const [name, setName] = useState('');

   <input
     type="text"
     value={name}
     onChange={(e) => setName(e.target.value)}
   />
   ```
4. Explain: "The input doesn't manage its own value. React state is the single source of truth."
5. Create state for each field: name, email, message
6. Show an alternative: one state object for the whole form
   ```jsx
   const [formData, setFormData] = useState({ name: '', email: '', message: '' });
   ```
7. Handle submission:
   - `onSubmit` on the form element
   - `e.preventDefault()` to stop page reload
   - Read values from state (not from the DOM)
   - Display submitted data in a list below the form
8. Add basic validation: check if fields are empty, show error messages
9. Clear the form after submission by resetting state

## Prompting coaching
"For forms: `create a controlled input for email` or `add validation to my form`. React form patterns are well-defined, so Claude knows exactly what to generate."

## Quiz questions
- What is a controlled component in React?
- Why does the input need both `value` and `onChange`?
- How do you prevent the page from refreshing on form submit in React?

## Hints (only if stuck)
1. Every input needs `value={stateVariable}` and `onChange={(e) => setStateVariable(e.target.value)}`
2. Handle submit on the `<form onSubmit={handleSubmit}>` element, not the button
3. Clear the form by setting all state values back to empty strings
