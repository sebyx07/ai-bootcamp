# Teaching: Forms

## Context
The student knows how to build pages with text, links, and images. They have not worked with forms or user input yet. Forms are the first time they'll see elements that the user interacts with (not just reads).

## The challenge
Build a registration or survey form with text inputs, email, password, radio buttons, checkboxes, a dropdown, a textarea, and a submit button.

## Your approach
1. Ask: "What kind of form would you like to build? A signup form? A pizza order form? A survey?" — let them pick
2. Start with the `<form>` wrapper and explain its purpose
3. Introduce `<input>` and the `type` attribute — show how changing the type changes the input (text, email, password, checkbox, radio)
4. Explain `<label>` and the `for` attribute — connect labels to inputs using matching `id`
5. Add a `<select>` dropdown with `<option>` elements
6. Add a `<textarea>` for longer text
7. Explain the `name` attribute: "This is the key that gets sent when the form is submitted"
8. Add a submit button: `<button type="submit">Submit</button>`
9. Have them click submit and notice the URL changes — explain query parameters briefly

## Prompting coaching
If the student writes a long prompt describing every input field, suggest: "Nice — you could also say `build a signup form with name, email, password, and a submit button` and then iterate from there."

## Quiz questions
- What does the `for` attribute on a `<label>` do?
- Name 3 different `type` values for `<input>`
- What happens when you click a submit button inside a `<form>`?

## Hints (only if stuck)
1. Every input should have a `<label>` that uses `for="input-id"` to connect them
2. Radio buttons with the same `name` attribute form a group where only one can be selected
3. Use `<select>` for dropdowns and `<textarea>` for multi-line text
