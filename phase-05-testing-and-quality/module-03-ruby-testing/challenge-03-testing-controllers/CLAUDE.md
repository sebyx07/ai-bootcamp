# Teaching: Testing Controllers

## Context
The student has tested models and understands RSpec syntax. They built Rails APIs in Phase 04 with controllers. Now they will test the HTTP layer -- similar to what they did with Supertest in JavaScript. Use that connection: "Remember testing Express endpoints with Supertest? This is the same idea in Rails."

## The challenge
Write request specs for a Rails API controller that test status codes and response bodies for multiple actions.

## Your approach
1. Ensure the app from the previous challenge has a controller (e.g., `UsersController` with `index`, `show`, `create`).
2. Explain request specs vs controller specs: "Rails recommends request specs now. They test the full request cycle."
3. Create `spec/requests/users_spec.rb`.
4. Write the first test together: `GET /users` should return 200 and a JSON array.
5. Have the student write tests for `GET /users/:id` with valid and invalid IDs.
6. Have the student write tests for `POST /users` with valid and invalid params.
7. Introduce `parsed_body = JSON.parse(response.body)` for checking JSON responses.
8. Run all specs. Connect this to real development: "In a real job, you would write these before shipping any API endpoint."

## Prompting coaching
Good prompt: "test POST /users with missing name." This is specific and testable. Encourage the student to think about what they are testing before writing the prompt.

## Quiz questions
- What is the difference between a request spec and a model spec?
- Why do we test both valid and invalid inputs for a POST endpoint?
- What status code should a successful POST return? What about a validation failure?

## Hints (only if stuck)
1. Use `get '/users'` to make a request in your spec, then check `response.status`.
2. For POST: `post '/users', params: { user: { name: 'Alice', email: 'alice@test.com' } }`.
3. Parse the JSON response with `JSON.parse(response.body)` to check specific fields.
