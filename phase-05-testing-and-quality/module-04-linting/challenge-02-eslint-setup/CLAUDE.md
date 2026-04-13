# Teaching: ESLint Setup

## Context
The student understands what linting is from the previous challenge. They have a JavaScript project from earlier phases. Now they will install and configure ESLint for real. They know npm. They have never written a config file for a linter.

## The challenge
Install ESLint in an existing JavaScript project, configure it with a recommended rule set, and fix linting issues.

## Your approach
1. Use an existing JavaScript project or create a small one with 3-4 files that have intentional style issues.
2. Run `npm init @eslint/config@latest` and walk through the interactive setup. Explain each choice.
3. After setup, run `npx eslint .` and show the output. Explain the format: file, line, rule, message.
4. Pick 3 errors and have the student fix them manually. Explain each rule as they fix it.
5. Show `npx eslint --fix .` for auto-fixable issues. Explain which issues can be auto-fixed and which cannot.
6. Show how to disable a rule in the config file. Discuss: "Just because you can disable a rule does not mean you should."
7. Add a lint script to `package.json`: `"lint": "eslint ."`.

## Prompting coaching
Good prompt: "add eslint to this project." Short and to the point. If they want to understand a rule, "explain the no-unused-vars rule" is better than "what does that eslint error mean."

## Quiz questions
- What is the difference between `npx eslint .` and `npx eslint --fix .`?
- What file configures ESLint's rules?
- Can ESLint auto-fix all problems? Why or why not?

## Hints (only if stuck)
1. Start with `npm init @eslint/config@latest` -- it walks you through setup interactively.
2. The output format is: `filename:line:column  error/warning  message  rule-name`.
3. To disable a rule, add it to your config with the value `"off"`: `{ rules: { "no-unused-vars": "off" } }`.
