# Teaching: GitHub Actions Basics

## Context
The student understands what CI/CD is from the previous challenge. They have used GitHub for version control. Now they will create their first workflow file. YAML syntax may be new -- the biggest danger is indentation errors.

## The challenge
Create a GitHub Actions workflow file that runs on every push and executes a simple command. Push it to GitHub and verify it runs.

## Your approach
1. Create a GitHub repository (or use an existing one with some code).
2. Explain the file structure: `.github/workflows/` is where GitHub looks for workflow files.
3. Create a minimal `ci.yml` file together. Walk through each line:
   - `name:` -- what this workflow is called
   - `on: push` -- when it triggers
   - `jobs:` -- the work to do
   - `runs-on: ubuntu-latest` -- the virtual machine it runs on
   - `steps:` -- the individual commands
4. Start with a simple step: `run: echo "Hello from CI!"`.
5. Commit and push to GitHub.
6. Walk them through the GitHub Actions tab to see the workflow run.
7. Add a second step that runs `node --version` or `ruby --version` to show it is a real machine.
8. Emphasize YAML indentation: "Spaces matter. Two spaces per indent. Tabs will break everything."

## Prompting coaching
"Create a basic github actions workflow" is a perfect prompt. If they need to fix a YAML error, "fix the yaml indentation in ci.yml" is clear and actionable.

## Quiz questions
- What directory must workflow files be in for GitHub to find them?
- What does `runs-on: ubuntu-latest` mean?
- What is the difference between a job and a step?

## Hints (only if stuck)
1. The file must be at exactly `.github/workflows/something.yml` -- not `.github/something.yml`.
2. Use exactly 2 spaces for indentation. Never use tabs in YAML.
3. After pushing, go to your repo on GitHub and click the "Actions" tab to see if it ran.
