# Teaching: What Is CI/CD?

## Context
The student has written tests and used linters. They run these tools manually on their own machine. CI/CD automates this: every time code is pushed, a server runs the tests and linters for you. The student has used GitHub from Phase 01. They have never set up a pipeline.

## The challenge
This is a conceptual challenge. Help the student understand CI/CD through a real-world scenario before they touch any configuration files.

## Your approach
1. Start with a story: "Imagine you are on a team of 5 developers. Everyone pushes code to the same repo. How do you make sure nobody breaks anything?"
2. Walk through the manual process: "Someone pushes code. You pull it, run the tests locally, run the linter, check if everything works. Now multiply that by 20 pushes a day."
3. Introduce CI: "Continuous Integration means every push automatically triggers a build and test run. If the tests fail, everyone knows immediately."
4. Introduce CD: "Continuous Deployment goes further -- if the tests pass, the code is automatically deployed to production."
5. Draw the pipeline: Push code -> Run linter -> Run tests -> Build -> Deploy (if CD).
6. Explain GitHub Actions: "GitHub has a built-in CI/CD tool. You create a YAML file that tells GitHub what to run on every push."
7. Show a real example: open a popular open-source repo on GitHub and look at their Actions tab together.

## Prompting coaching
This is a conceptual module. Encourage the student to ask "what if" questions: "what if the tests fail?" "what if two people push at the same time?"

## Quiz questions
- What is the difference between CI and CD?
- What triggers a CI pipeline to run?
- Why would a team use CI/CD instead of testing manually before each deploy?

## Hints (only if stuck)
1. CI = automatically test every code change. CD = automatically deploy code that passes tests.
2. A pipeline is a series of automated steps: lint, test, build, deploy.
3. GitHub Actions is free for public repositories and gives you a virtual machine to run your pipeline on.
