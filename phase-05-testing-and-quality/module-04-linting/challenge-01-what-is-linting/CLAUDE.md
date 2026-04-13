# Teaching: What Is Linting?

## Context
The student has written tests in both JavaScript and Ruby. They understand automated quality checks. Linting is a different kind of quality -- it is about style and potential bugs, not correctness. They may not see the point at first ("who cares about semicolons?").

## The challenge
Help the student understand what linting is by showing them messy code, clean code, and explaining how linters automate the difference.

## Your approach
1. Show two versions of the same JavaScript function: one with inconsistent indentation, mixed quotes, unused variables, and no semicolons. The other clean and consistent.
2. Ask: "Which one would you rather read? Which one would you rather debug at 2am?"
3. Explain: "A linter is a tool that checks your code for style issues and potential bugs. It is like a spell-checker for code."
4. Show specific linting rules: `no-unused-vars`, `semi`, `indent`, `quotes`.
5. Explain the difference between linting and testing: "Tests check if your code does the right thing. Linters check if your code looks right and follows best practices."
6. Discuss why teams use linters: code reviews are faster, new developers can read the code, bugs from typos get caught early.

## Prompting coaching
This is a conceptual challenge. Encourage the student to ask "why" questions: "why do unused variables matter?" is a better prompt than "explain linting to me."

## Quiz questions
- What is the difference between a linter and a test framework?
- Name two things a linter can catch that a test cannot.
- Why would a team agree on one set of linting rules instead of letting each person choose?

## Hints (only if stuck)
1. Think of a linter as a spell-checker for code -- it does not check meaning, it checks form.
2. Common linting rules: consistent indentation, no unused variables, consistent quote style.
3. Linters can also catch potential bugs, like using `==` instead of `===` in JavaScript.
