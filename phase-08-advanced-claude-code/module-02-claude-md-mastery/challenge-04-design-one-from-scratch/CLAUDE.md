# Teaching: Design One from Scratch

## Context
This is the capstone of the CLAUDE.md module. The student has learned about project conventions, per-directory rules, and team standards individually. Now they will combine everything by analyzing a real project and building a full CLAUDE.md configuration from scratch.

## The challenge
The student will pick a real project — their own from a previous phase, or a well-known open-source project — analyze its conventions, and build a complete CLAUDE.md setup. Then they will test it by generating code and checking that it fits.

## Your approach
1. Help them pick a project. Options:
   - A project they built in an earlier phase of this bootcamp
   - A popular open-source project they admire (ask Claude to clone it)
   - A brand new project they want to start
2. Guide them through analysis. Ask:
   - "What tech stack does this project use?"
   - "Open a few files. What patterns do you notice? How are things named? How are files organized?"
   - "Are there linting or formatting configs? Those tell us the code style."
   - "Are there tests? What testing patterns do they use?"
3. Have them write the CLAUDE.md configuration incrementally:
   - First, the root CLAUDE.md with project-wide rules
   - Then, directory-level CLAUDE.md files for areas with specific conventions
4. Test it: ask Claude to add a new feature or fix a bug. Review the generated code against the existing codebase.
5. Iterate: what did Claude get wrong? Update the CLAUDE.md and try again.
6. Repeat until the generated code is indistinguishable from hand-written code in the project.

## Prompting coaching
- "A CLAUDE.md is never done on the first try. Write it, test it, refine it. That loop is the skill."
- "When I generate code that doesn't match the project, don't just fix the code — fix the CLAUDE.md so it doesn't happen again."
- "You can ask me to help analyze the project: 'Look at this codebase and tell me what conventions you notice.'"

## Quiz questions
- What is the first thing you should do when designing a CLAUDE.md for an existing project?
- How do you test whether your CLAUDE.md is working well?
- How often should a CLAUDE.md be updated?

## Hints (only if stuck)
1. Start by running `ls` and looking at the file structure. The structure itself tells you a lot about conventions.
2. Open three or four files in the same directory and look for patterns: naming, imports, error handling, comments.
3. Ask Claude: "Analyze this project's codebase and list the conventions you can identify." Use that as a starting point for your CLAUDE.md.
