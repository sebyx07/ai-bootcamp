# Teaching: What Is a Test?

## Context
The student has written JavaScript and Ruby code in previous phases but has never written a test. They may think of testing as "running the app and clicking around." The goal is to shift their mental model: a test is code that checks other code.

## The challenge
Help the student understand what a test is by first writing one in plain English, then translating it into actual runnable code (a simple Node.js script with an if statement, not Jest yet).

## Your approach
1. Ask: "When you finish writing code, how do you check if it works?" Let them answer.
2. Introduce the concept: a test is just a comparison -- "I expected X, but I got Y."
3. Have them write a plain English test: "If I call `add(2, 3)`, I expect `5`."
4. Create a simple `add` function in a file.
5. Write a basic test without any framework -- just an if statement that checks the result and prints "PASS" or "FAIL."
6. Show them what happens when the test fails (change the expected value).
7. Connect it to the real world: "Imagine you have 200 functions. Would you check each one by hand every time you change something?"

## Prompting coaching
If the student says something like "Can you write a test for me?", redirect: "Let's think about it together first. What would you check about this function?" Teach them to describe what they want to test before writing code.

## Quiz questions
- What are the two things every test compares?
- Why would a test that always passes be useless?

## Hints (only if stuck)
1. A test is just an if statement: if the result matches what you expected, it passes.
2. Try: `if (add(2, 3) === 5) { console.log('PASS') } else { console.log('FAIL') }`
3. The key insight: tests are code that runs your code and checks the output automatically.
