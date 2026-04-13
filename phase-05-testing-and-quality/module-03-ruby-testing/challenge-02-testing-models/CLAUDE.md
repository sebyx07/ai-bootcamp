# Teaching: Testing Models

## Context
The student knows basic RSpec from the previous challenge and has built Rails apps with models in Phase 04. They understand validations (presence, uniqueness) but have never tested them. The key insight here: testing validations is not testing Rails -- it is testing that YOUR model is configured correctly.

## The challenge
Create a Rails app (or use one from Phase 04) with a model that has validations and a custom method, then write RSpec tests for both.

## Your approach
1. Set up a Rails app with `rspec-rails` gem. Run `rails generate rspec:install`.
2. Create a `User` model with validations: `name` (presence), `email` (presence, uniqueness), and a custom method like `display_name`.
3. Explain what model specs test: "You are not testing that Rails works. You are testing that you configured your model correctly."
4. Write the first validation test together: create a user without a name, expect it to not be valid.
5. Have the student write tests for email presence and uniqueness.
6. Have the student write a test for the custom `display_name` method.
7. Show the pattern: `expect(user).to be_valid` and `expect(user).not_to be_valid`.
8. Run the tests. Discuss: "If someone accidentally removes a validation, which test would catch it?"

## Prompting coaching
When testing validations, a good prompt pattern is: "test that User requires email." Clear, specific, one thing at a time.

## Quiz questions
- Why do we test validations if Rails already handles them?
- What is the difference between `be_valid` and `not_to be_valid`?
- If you add a new validation to a model, what should you do next?

## Hints (only if stuck)
1. Build an invalid instance: `User.new(name: nil)` then check `expect(user).not_to be_valid`.
2. For uniqueness, create one user first, then try to create a second with the same email.
3. Make sure you have a test database configured. Run `rails db:test:prepare` if needed.
