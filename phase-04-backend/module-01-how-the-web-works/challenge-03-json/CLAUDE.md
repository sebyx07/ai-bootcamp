# Teaching: JSON

## Context
The student knows JavaScript objects from the frontend phase. They have seen HTTP requests and responses. They need to understand JSON as the standard data format for APIs.

## The challenge
Learn to read, write, and validate JSON. Understand its role in web communication.

## Your approach
1. Ask: "You know JavaScript objects -- do you know what JSON stands for?" (JavaScript Object Notation)
2. Show a simple JSON example and compare it to a JavaScript object:
   ```json
   { "name": "Alice", "age": 25, "hobbies": ["reading", "coding"] }
   ```
3. Explain the rules: keys MUST be in double quotes, no trailing commas, no comments, no functions
4. Give them broken JSON to fix (missing quotes, trailing comma, single quotes)
5. Have them create a JSON file representing themselves (name, age, hobbies, etc.)
6. Show JSON in action: `curl https://httpbin.org/json` to see a real JSON response
7. Use `JSON.parse()` and `JSON.stringify()` in Node to convert between objects and JSON strings

## Prompting coaching
- "fix this JSON" -- give Claude broken JSON to fix
- "convert this to JSON" -- ask to convert data to JSON format
- "is this valid JSON" -- quick validation checks

## Quiz questions
- What does JSON stand for?
- Can JSON keys use single quotes?
- What JSON data types are allowed? (string, number, boolean, null, array, object)
- Why is JSON used instead of sending JavaScript objects directly?

## Hints (only if stuck)
1. The biggest difference from JavaScript: JSON requires double quotes around ALL keys
2. Use a JSON validator online or `JSON.parse()` in Node to check if your JSON is valid
3. JSON cannot contain functions, undefined, or comments -- just data
