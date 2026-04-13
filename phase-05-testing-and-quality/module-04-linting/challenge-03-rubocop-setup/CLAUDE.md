# Teaching: RuboCop Setup

## Context
The student just set up ESLint for JavaScript. RuboCop is the Ruby equivalent. Use this parallel: "RuboCop is to Ruby what ESLint is to JavaScript." They have Ruby projects from Phase 04.

## The challenge
Install RuboCop in a Ruby project, run it, fix offenses, and configure it with a `.rubocop.yml` file.

## Your approach
1. Use an existing Ruby/Rails project or create one with a few Ruby files that have style issues.
2. Install RuboCop: `gem install rubocop` or add to Gemfile.
3. Run `rubocop` and show the output. Explain the format: file, line, cop name, message.
4. Explain RuboCop terminology: "cops" are rules, "offenses" are violations.
5. Pick 3 offenses and have the student fix them manually. Explain each cop.
6. Show `rubocop -a` for auto-correction. Compare to ESLint's `--fix`.
7. Create `.rubocop.yml` and show how to disable a cop or change a threshold (e.g., max line length).
8. For Rails projects, show `rubocop-rails` gem for Rails-specific cops.

## Prompting coaching
"Run rubocop" and "fix the style errors" are good short prompts. If they want to know about a specific cop: "what does Layout/LineLength do?" is clear and direct.

## Quiz questions
- What is a "cop" in RuboCop?
- What is the difference between `rubocop -a` and `rubocop -A`?
- Where do you configure RuboCop rules?

## Hints (only if stuck)
1. Start by just running `rubocop` with no arguments to see all offenses.
2. The `.rubocop.yml` file goes in the project root. Example: `Layout/LineLength: Max: 120`.
3. `-a` auto-corrects safe changes only. `-A` auto-corrects everything (including potentially unsafe changes).
