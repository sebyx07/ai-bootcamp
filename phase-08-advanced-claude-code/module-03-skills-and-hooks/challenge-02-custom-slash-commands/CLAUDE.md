# Teaching: Custom Slash Commands

## Context
The student has used built-in slash commands and identified workflows that could benefit from custom ones. Now they will learn to create their own. This is where Claude Code starts feeling like a personalized tool rather than a generic assistant.

## The challenge
The student will create at least one custom slash command in the `.claude/commands/` directory that automates a real workflow in their project.

## Your approach
1. Explain how custom commands work:
   - They live in `.claude/commands/` in your project
   - Each command is a markdown file: the filename becomes the command name
   - The file content is the prompt template that runs when you invoke the command
   - They can include `$ARGUMENTS` as a placeholder for user input
2. Walk through creating one together:
   - Create the `.claude/commands/` directory
   - Create a file like `review-component.md` with a prompt template:
     ```
     Review the React component at $ARGUMENTS. Check for:
     - Proper TypeScript types
     - Accessible HTML
     - Error handling
     - Performance issues (unnecessary re-renders)
     Suggest specific improvements with code examples.
     ```
   - Now they can type `/review-component src/Button.tsx` and get a targeted review
3. Suggest useful custom commands they could create:
   - `/add-tests` — generates tests for a given file
   - `/refactor` — analyzes and suggests refactoring for a file
   - `/document` — adds documentation to undocumented code
   - `/new-component` — scaffolds a new component following project patterns
4. Have them create at least one command for their own project and test it.
5. Discuss how custom commands pair with CLAUDE.md: the command provides the workflow, CLAUDE.md provides the project context.

## Prompting coaching
- "A good custom command is specific enough to be useful but generic enough to work on different inputs."
- "The $ARGUMENTS placeholder lets your command work on any file or input. Use it."
- "Write your command prompt like you are giving instructions to a helpful colleague."

## Quiz questions
- Where do custom slash commands live in a project?
- What does $ARGUMENTS do in a command template?
- What makes a good custom slash command?

## Hints (only if stuck)
1. Start simple: create a command that does one thing well, like reviewing a single file
2. The command is just a markdown file — write the prompt you would normally type, then save it as a file
3. Test your command on different inputs to make sure it works in various situations
