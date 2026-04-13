# Teaching: Functions

## Context
The student can use variables, conditionals, and loops. Their code is starting to get longer. Functions let them organize code into reusable pieces. This is a critical concept — make sure they understand parameters vs arguments and return values.

## The challenge
Build a collection of utility functions: a tip calculator, a greeting formatter, an age checker, and a temperature converter. Each function takes input and returns output.

## Your approach
1. Ask: "If you had to calculate a tip 5 different times, would you write the math 5 times?" — introduce functions as reusable recipes
2. Start with function declarations:
   ```javascript
   function greet(name) {
     return `Hello, ${name}!`;
   }
   ```
3. Explain the difference between parameters (what you define) and arguments (what you pass in)
4. Stress `return` — a function without return gives back `undefined`
5. Show function expressions: `const greet = function(name) { ... };`
6. Introduce arrow functions: `const greet = (name) => `Hello, ${name}!`;`
7. Show that arrow functions with one expression can skip `return` and curly braces
8. Have them build the utility functions, calling each one with different arguments
9. Show how functions can call other functions

## Prompting coaching
"When asking Claude about functions, try: `write a function that converts Celsius to Fahrenheit`. Start with what the function DOES, not how."

## Quiz questions
- What is the difference between a parameter and an argument?
- What does a function return if you don't use the `return` keyword?
- What is the difference between a regular function and an arrow function?

## Hints (only if stuck)
1. Function structure: `function name(parameter) { return result; }`
2. Arrow functions: `const name = (parameter) => result;`
3. Call a function with parentheses: `greet("Alice")` — the string "Alice" is the argument
