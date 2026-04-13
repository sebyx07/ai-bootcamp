# Teaching: Auto-Run Tests on Push

## Context
The student has a working GitHub Actions workflow from the previous challenge and test suites from earlier modules. Now they combine everything: push code, automatically lint it, and run tests. This is real CI.

## The challenge
Extend the GitHub Actions workflow to install dependencies, run the linter, and run the test suite. Then demonstrate both a passing and failing pipeline.

## Your approach
1. Start with the workflow file from the previous challenge.
2. Choose either their JavaScript project (with Jest + ESLint) or Ruby project (with RSpec + RuboCop).
3. Add steps to the workflow:
   - Checkout code: `uses: actions/checkout@v4`
   - Set up Node.js (or Ruby): `uses: actions/setup-node@v4` with version
   - Install dependencies: `run: npm install` (or `bundle install`)
   - Run linter: `run: npx eslint .` (or `bundle exec rubocop`)
   - Run tests: `run: npm test` (or `bundle exec rspec`)
4. Commit and push. Watch it run in the Actions tab.
5. If it passes, celebrate: "Your first real CI pipeline!"
6. Now break something on purpose: add a failing test or a lint error. Push it.
7. Show the red X on GitHub. Explain: "This is exactly what CI is for. You caught the problem before anyone else was affected."
8. Fix the issue, push again, see the green checkmark.

## Prompting coaching
"Add test running to the github actions workflow" is a good prompt. "Why did the pipeline fail?" is a great debugging prompt -- encourage the student to read the logs in the Actions tab before asking Claude.

## Quiz questions
- In what order should your pipeline run: tests first or linter first? Why?
- If the linter step fails, do the tests still run?
- How would you add a step to deploy your app only if tests pass?

## Hints (only if stuck)
1. Make sure `actions/checkout@v4` is your first step -- without it, the workflow cannot see your code.
2. If `npm test` fails with "no tests found," make sure Jest is in `devDependencies` and the test script is configured in `package.json`.
3. Each step runs independently. If a step fails, subsequent steps do not run (by default). This is why linting should come before testing.
