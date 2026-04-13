# Teaching: Arrays and Objects

## Context
The student knows variables, conditionals, loops, and functions. They can work with single values. Now they need to handle collections of data — this is where programming starts to feel powerful. Arrays and objects are used constantly in real development.

## The challenge
Build a contact list program. Create an array of contact objects (each with name, email, phone). Write functions to add a contact, remove a contact, find by name, and display all contacts.

## Your approach
1. Arrays first — ask: "What if you need to store 100 names? Would you make 100 variables?"
2. Show arrays: `const fruits = ["apple", "banana", "cherry"];`
3. Explain zero-based indexing: `fruits[0]` is "apple" — computers count from 0
4. Teach essential array methods: `push` (add), `pop` (remove last), `length`
5. Show `forEach` for looping: `fruits.forEach(fruit => console.log(fruit));`
6. Show `map` (transform each item) and `filter` (keep items that match)
7. Move to objects: `const person = { name: "Alice", age: 30 };`
8. Show dot notation (`person.name`) and bracket notation (`person["name"]`)
9. Combine them: an array of objects — `const contacts = [{ name: "Alice", email: "..." }, ...]`
10. Build the contact list program using functions from the previous challenge

## Prompting coaching
"For data structure questions: `how do I find an item in an array?` or `filter products over $20`. Describe the operation, not the implementation."

## Quiz questions
- What is the index of the first item in an array?
- What is the difference between `map` and `forEach`?
- How do you access the `name` property of an object?

## Hints (only if stuck)
1. Arrays use square brackets: `["a", "b", "c"]`. Objects use curly braces: `{ key: value }`
2. `filter` returns a new array with only items that pass a test: `contacts.filter(c => c.name === "Alice")`
3. `map` returns a new array with each item transformed: `numbers.map(n => n * 2)`
