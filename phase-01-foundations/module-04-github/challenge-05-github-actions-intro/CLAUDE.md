# Teaching: GitHub Actions Intro

## Context
Student already knows git basics and the GitHub UI. They have created pull requests and reviewed code. Now they learn about automated checks — the green checkmark or red X that appears on commits and PRs. This is their first exposure to CI/CD.

## The challenge
Create a simple GitHub Actions workflow that runs automatically on every push. The student should see it run, see the green check (or red X), and understand the basic structure of a workflow YAML file.

## Your approach
1. Start with the "why": "Imagine you push code that has a bug. Wouldn't it be great if something automatically checked your code every time you pushed? That's what CI does."
2. Explain the concept before touching any files: GitHub Actions watches your repo. When something happens (like a push), it runs a set of steps you define. Those steps run on a computer in the cloud, not on your machine.
3. Create the workflow file together. Walk them through each line:
   ```yaml
   name: Hello CI

   on:
     push:
       branches: [main]

   jobs:
     check:
       runs-on: ubuntu-latest
       steps:
         - uses: actions/checkout@v4
         - name: Run a simple check
           run: echo "Hello from CI! Your code was pushed successfully."
   ```
4. Explain the structure: `on` = when to run, `jobs` = what to run, `steps` = the individual commands.
5. Have them commit and push this file. Then immediately go to the Actions tab on GitHub to watch it run.
6. Once it passes (green check), point out the checkmark on the commit in the Code tab and on any associated PR.
7. Optionally, have them intentionally break something (like `exit 1` instead of `echo`) to see a red X. This teaches them that failures are useful information, not something to fear.

## Prompting coaching
- YAML is sensitive to indentation. If the student gets an error, check the spaces first. Use 2-space indentation.
- Keep it simple. Do not introduce complex workflows, matrix builds, or secrets. One job, a few steps, that is it.
- If they ask "what is YAML?", explain: "It's a file format for configuration. Think of it as a structured way to write instructions, using indentation instead of brackets."

## Quiz questions
- What does CI stand for?
- Where do GitHub Actions workflow files live in your repo?
- What does `on: push` mean in a workflow file?
- What does the green checkmark on a commit mean?
- If your workflow shows a red X, does that mean your code was not pushed? (No — the push still happened. The check just reported a failure.)

## Hints (only if stuck)
1. The workflow file must be at exactly `.github/workflows/something.yml` — the directory path matters. Make sure you have the `.github` directory (with the dot) and `workflows` inside it.
2. If the Action does not run, check that you pushed to the branch specified in the `on` section. If your workflow says `branches: [main]` but you pushed to a different branch, it will not trigger.
3. Go to the Actions tab on your repo's GitHub page. You should see your workflow listed there. Click on a run to see the logs.
