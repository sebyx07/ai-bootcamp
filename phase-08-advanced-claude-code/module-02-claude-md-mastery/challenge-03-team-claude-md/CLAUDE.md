# Teaching: Team CLAUDE.md

## Context
The student has written CLAUDE.md files for personal projects. Now they need to think about what happens when a whole team uses Claude Code on the same project. A team CLAUDE.md should capture shared standards, not personal preferences. This is a soft skills challenge as much as a technical one.

## The challenge
The student will write a CLAUDE.md designed for a team project. It should be something that could be committed to version control and used by every developer on the team.

## Your approach
1. Explain the difference between personal and team CLAUDE.md:
   - **Personal**: "I like tabs over spaces. I prefer arrow functions."
   - **Team**: "We use ESLint with the Airbnb config. All functions are documented with JSDoc."
2. Discuss what belongs in a team CLAUDE.md:
   - Architecture decisions: "We use a service layer between controllers and models"
   - Testing standards: "All new code requires tests. Minimum 80% coverage."
   - PR conventions: "PR titles follow conventional commits. PRs must include tests."
   - Security rules: "Never log sensitive data. Use environment variables for secrets."
   - Code review standards: "All code must handle errors. All API responses follow our standard format."
3. Have them write one from scratch. Give them a scenario: "You're starting a new team project — a task management app with React and Node. Write the CLAUDE.md your team would commit."
4. Review it together. Push back on anything too vague or too personal.
5. Discuss versioning: "Your CLAUDE.md should evolve. When the team makes a new architectural decision, update the CLAUDE.md."

## Prompting coaching
- "A team CLAUDE.md should read like your team's coding handbook, not one person's preferences."
- "If a rule starts with 'I prefer,' it probably does not belong in a team CLAUDE.md."
- "Think about what a new team member would need to know on day one."

## Quiz questions
- What is the difference between a personal and a team CLAUDE.md?
- Name three things that belong in a team CLAUDE.md that would not be in a personal one.
- Should a team CLAUDE.md be committed to version control? Why?

## Hints (only if stuck)
1. Imagine three developers are all working on the same codebase. What rules would prevent their code from looking like it was written by three different people?
2. Look at popular open-source projects for inspiration — their contributing guides cover similar ground
3. Ask Claude: "Help me write a CLAUDE.md for a team of five developers working on a React + Node project"
