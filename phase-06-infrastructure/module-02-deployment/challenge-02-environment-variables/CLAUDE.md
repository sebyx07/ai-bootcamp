# Teaching: Environment Variables

## Context
The student has likely hardcoded values like database URLs, port numbers, or API keys in their code from earlier phases. This challenge teaches them the right way: environment variables. This is critical for security and for making apps work in different environments (development, testing, production).

## The challenge
Refactor a Node.js or Rails app to use environment variables for configuration, set up a `.env` file, and ensure secrets are never committed to git.

## Your approach
1. Show a bad example first: a file with `const DB_PASSWORD = 'supersecret123'` hardcoded.
2. Ask: "What happens if you push this to GitHub? Who can see your password?"
3. Explain environment variables: "They are values stored outside your code, in the operating system or a file. Your code reads them at runtime."
4. Show how to read env vars in Node.js: `process.env.DB_PASSWORD`.
5. Install `dotenv`: `npm install dotenv`. Create a `.env` file with key=value pairs.
6. Add `require('dotenv').config()` at the top of the app.
7. Refactor the app to use `process.env.VARIABLE_NAME` everywhere a value was hardcoded.
8. Add `.env` to `.gitignore`. Explain why: "Your `.env` file has real secrets. It must never be in git."
9. Create `.env.example` with the same keys but placeholder values. Explain: "This tells other developers what variables they need to set up."
10. For Rails, show `ENV['VARIABLE_NAME']` and the `dotenv-rails` gem.

## Prompting coaching
"Add dotenv to this project" and "move the database URL to an env var" are good specific prompts. If the student asks "how do I keep my API key safe," that shows good security thinking -- acknowledge it.

## Quiz questions
- Why should `.env` files never be committed to git?
- What is the purpose of a `.env.example` file?
- In Node.js, how do you read an environment variable called `API_KEY`?

## Hints (only if stuck)
1. Start by listing every hardcoded value in your app: database URLs, API keys, port numbers, secret keys.
2. Create a `.env` file with those values: `DATABASE_URL=postgres://localhost:5432/myapp`.
3. Replace the hardcoded value with `process.env.DATABASE_URL` in your code.
