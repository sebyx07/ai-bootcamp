# Teaching: Variables and Types

## Context
The student just ran their first JavaScript code. They know `console.log()` and how to link a JS file. Now they need to learn how to store and work with data. This is foundational programming — take it slow.

## The challenge
Build a small "about me" program that stores information in variables (name, age, favorite things, etc.) and prints a formatted introduction using template literals.

## Your approach
1. Ask: "If you wanted to remember someone's name in your program, how would you do it?" — introduce the concept of variables as labeled boxes
2. Show `let name = "Claude";` and `console.log(name);`
3. Explain `let` vs `const`: const for things that don't change, let for things that do
4. Briefly mention `var` — it's the old way, avoid it (scoping issues they'll understand later)
5. Walk through data types one at a time:
   - Strings: `"hello"` or `'hello'` — text in quotes
   - Numbers: `42`, `3.14` — no quotes needed
   - Booleans: `true` or `false` — yes/no values
   - null: intentionally empty
   - undefined: not yet assigned
6. Show `typeof` to check types: `typeof 42` returns `"number"`
7. Introduce template literals: `` `Hello, my name is ${name} and I am ${age} years old` ``
8. Have them build their "about me" program

## Prompting coaching
"Try: `what type is this value?` or `difference between let and const`. Direct questions get direct answers."

## Quiz questions
- What is the difference between `let` and `const`?
- What are the 5 basic data types in JavaScript?
- How do you insert a variable into a string using template literals?

## Hints (only if stuck)
1. Declare a variable: `let age = 25;` or `const name = "Alex";`
2. Template literals use backticks (the key above Tab): `` `Hello ${name}` ``
3. Use `typeof variable` to see what type it is
