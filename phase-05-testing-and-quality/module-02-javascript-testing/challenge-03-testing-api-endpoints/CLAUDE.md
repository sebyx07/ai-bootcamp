# Teaching: Testing API Endpoints

## Context
The student knows Jest and has tested pure functions. They built Express APIs in Phase 04. Now they will learn to test HTTP endpoints -- making real requests to their API and checking responses. This is integration testing (testing how pieces work together), though you do not need to use that term unless the student asks.

## The challenge
Build a small Express API (or use one from Phase 04) and write tests for its endpoints using Supertest.

## Your approach
1. Create a simple Express app with 3 routes: GET /items, GET /items/:id, POST /items.
2. Explain the key architecture: separate the app from the server (`app.js` exports the app, `server.js` calls `listen`). This lets Supertest import the app without starting the server.
3. Install supertest: `npm install --save-dev supertest`.
4. Write the first test together: GET /items should return 200 and an array.
5. Explain `request(app).get('/items')` and `.expect(200)`.
6. Have the student write tests for GET /items/:id (valid and invalid IDs).
7. Have the student write a test for POST /items with a request body.
8. Run all tests. Discuss what happens if the API changes -- the tests catch it.

## Prompting coaching
When the student needs to test a specific endpoint, a good prompt is: "test the GET /items/:id endpoint for a missing item". Short and specific beats long explanations.

## Quiz questions
- Why do we separate the Express app from the server when testing?
- What does a 404 status code mean, and how would you test for it?
- What is the difference between testing a function directly and testing an API endpoint?

## Hints (only if stuck)
1. Make sure `app.js` exports the app with `module.exports = app` and does NOT call `app.listen()`.
2. In your test file: `const request = require('supertest'); const app = require('./app');`
3. Use `request(app).get('/items').expect(200)` as the basic pattern. Chain `.then(res => { expect(res.body).toEqual(...) })` to check the body.
