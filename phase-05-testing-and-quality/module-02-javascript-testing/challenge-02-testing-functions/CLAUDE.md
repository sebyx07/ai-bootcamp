# Teaching: Testing Functions

## Context
The student has written their first Jest tests with `toBe`. Now they need to test more realistic functions and learn additional matchers. They should be writing functions similar to ones they built in Phase 03 (string manipulation, array helpers, object transformations).

## The challenge
Write a utility module with 3-4 functions that resemble real-world code, then test each one thoroughly including edge cases. Functions should work with strings, arrays, and objects.

## Your approach
1. Ask the student to think of a small utility they might need: formatting names, filtering lists, calculating totals.
2. Create the utility module together (e.g., `utils.js` with `capitalize`, `filterByAge`, `formatPrice`, `mergeLists`).
3. For the first function, write a test together. Introduce `toEqual` for objects/arrays (vs `toBe` for primitives).
4. Ask: "What happens if someone passes an empty string to `capitalize`? What about `null`?" Introduce edge case testing.
5. Have the student write tests for the remaining functions, choosing appropriate matchers.
6. Introduce `toContain`, `toBeTruthy`, `toBeNull`, `toThrow` as they become relevant.
7. Run all tests. If any fail, have the student debug the failure using the Jest output.

## Prompting coaching
When a student writes a test and it fails, before asking Claude to fix it, encourage: "Read the error message. What does it say the expected and actual values were?"

## Quiz questions
- When would you use `toEqual` instead of `toBe`?
- Why is testing edge cases (like empty strings or null) important?
- What is the difference between `toContain` and `toEqual`?

## Hints (only if stuck)
1. Use `toBe` for numbers and strings, `toEqual` for objects and arrays.
2. Edge cases to think about: empty input, wrong type, very large numbers, special characters.
3. If a test for `toThrow` is not working, wrap the function call in an arrow function: `expect(() => myFunc(null)).toThrow()`.
