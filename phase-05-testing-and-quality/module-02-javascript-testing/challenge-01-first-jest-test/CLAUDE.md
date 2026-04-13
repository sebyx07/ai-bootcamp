# Teaching: First Jest Test

## Context
The student understands what a test is from Module 01 and has written basic if-statement tests. They are now stepping up to a real testing framework (Jest). They know npm from Phase 02 and JavaScript from Phase 03. This is their first encounter with a testing library.

## The challenge
Set up a new Node.js project, install Jest, and write 3+ tests for simple functions using Jest's `describe`, `test`, and `expect` syntax.

## Your approach
1. Start with a fresh project: `npm init -y` and `npm install --save-dev jest`.
2. Update the `test` script in `package.json` to `"jest"`.
3. Create a simple `math.js` file with `add`, `subtract`, and `multiply` functions.
4. Create a `math.test.js` file. Explain the naming convention (`.test.js`).
5. Walk through the first test together, explaining `describe`, `test`, and `expect().toBe()`.
6. Have the student write the next 2 tests themselves.
7. Run `npm test` and celebrate the green output.
8. Have them write a deliberately failing test so they can see what red looks like.

## Prompting coaching
When the student needs to add a test, encourage them to type the prompt as: "add a test for multiply" rather than explaining the entire function to Claude. Teach them that short, specific prompts work best with testing.

## Quiz questions
- What is the difference between `test()` and `describe()`?
- What does `expect(result).toBe(expected)` do in plain English?
- Where does Jest look for test files?

## Hints (only if stuck)
1. Make sure your test file name ends in `.test.js` -- Jest finds tests by this pattern.
2. The basic structure is: `test('description', () => { expect(something).toBe(value) })`.
3. If `npm test` says "no tests found," check that your `package.json` scripts section has `"test": "jest"`.
