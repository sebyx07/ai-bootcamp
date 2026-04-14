# Teaching: Fill Forms and Interact

## Context
The student can navigate pages and click links. Now they need to learn how to interact with form elements — text fields, dropdowns, checkboxes, and submit buttons. This is essential for many automation tasks (logging in, searching, submitting data). Continue working in `workspace/phase-10/playwright-basics/`.

## The challenge
Write a script that fills out a form on a practice website, selects options, checks boxes, and submits the form.

## Your approach
1. Ask: "What different types of form elements have you seen on websites?" (Expected: text boxes, dropdowns, checkboxes, radio buttons, submit buttons)
2. Use `https://the-internet.herokuapp.com/` as a practice site — it has forms, checkboxes, dropdowns, etc.
3. Teach key form interaction methods:
   - `page.fill()` — type text into input fields
   - `page.selectOption()` — choose from a dropdown
   - `page.check()` / `page.uncheck()` — toggle checkboxes
   - `page.click()` on submit buttons — submit the form
   - `page.type()` vs `page.fill()` — type simulates keystrokes, fill replaces the value
4. Write a script that:
   - Goes to a form page (e.g., `/login`, `/dropdown`, `/checkboxes`)
   - Fills in form fields
   - Selects dropdown options
   - Checks/unchecks boxes
   - Submits and verifies the result
5. Show how to verify the form submission worked (check for success message, URL change, etc.)
6. Run in headed mode so they can watch the form being filled out
7. Ask the quiz questions

## Quiz questions
- What's the difference between `page.fill()` and `page.type()`?
- How would you select the third option in a dropdown?
- After submitting a form, how can your script verify it worked?

## Hints (only if stuck)
1. `page.fill('#username', 'myuser')` fills a text field — the first argument is the selector, the second is the text
2. For dropdowns, `page.selectOption('select', { value: 'option2' })` or `{ label: 'Option 2' }`
3. Always check what happens after submission — look for a success message or a URL change to confirm it worked
