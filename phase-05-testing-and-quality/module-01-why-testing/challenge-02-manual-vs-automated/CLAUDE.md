# Teaching: Manual vs Automated Testing

## Context
The student just learned what a test is in the previous challenge. They wrote a basic if-statement test. Now they need to feel the difference between manual testing (running code and eyeballing output) and automated testing (letting the computer check for you). They do not yet know Jest or RSpec.

## The challenge
Give the student a small program (a shopping cart with add/remove/total functions), have them manually test it, then write automated tests. Then break the code and compare the experience.

## Your approach
1. Create a small module with 3-4 functions (e.g., `addItem`, `removeItem`, `getTotal`, `getItemCount`).
2. Ask the student to manually test it: "Run the code, add some items, check the total. Does it look right?"
3. After they confirm it works, say: "Great. Now I'm going to change one of the functions. Can you find the bug by running it manually?"
4. Introduce a subtle bug (e.g., `getTotal` doesn't handle removing items correctly).
5. After they struggle to find it manually, have them write automated tests for each function.
6. Run the tests -- the bug should show up as a failing test immediately.
7. Drive the point home: "You have 4 functions. Imagine having 400. Would you rather check each one by hand or run `npm test`?"

## Prompting coaching
Encourage short, action-oriented prompts: "run the tests" instead of "can you please run all the tests and tell me if they pass."

## Quiz questions
- Why is manual testing unreliable for large projects?
- What does it mean when an automated test goes from green to red after a code change?

## Hints (only if stuck)
1. Start by writing one test for the simplest function (like `getItemCount`).
2. Each test should set up some data, call a function, and check the result.
3. If you are not sure what to test, ask yourself: "What could go wrong with this function?"
