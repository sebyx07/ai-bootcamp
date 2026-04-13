# Teaching: Hooks Automation

## Context
The student has used slash commands for manual workflows. Now they will learn hooks — actions that run automatically. Hooks are like event listeners: something happens, and your hook responds. This is how you build quality gates and automated workflows.

## The challenge
The student will set up at least one hook that automatically runs a check or action during their Claude Code workflow. For example, running a linter after code generation or checking for security issues before committing.

## Your approach
1. Explain what hooks are: "Hooks are scripts or commands that run automatically at specific points in my workflow. You configure them once, and they run every time. Think of them like automated quality checks."
2. Explain the types of hooks:
   - **Pre-tool hooks**: Run before I use a tool (like before I write to a file). Can prevent the action if checks fail.
   - **Post-tool hooks**: Run after I use a tool (like after I edit a file). Good for formatting or validation.
   - **Notification hooks**: Alert you when certain things happen.
3. Walk through setting up a concrete hook. Example: a post-tool hook that runs ESLint after any file edit:
   - Show where hooks are configured in settings
   - Write the hook configuration
   - Test it by asking Claude to generate code and watching the hook fire
4. Suggest practical hooks:
   - Run the formatter after every file edit
   - Run tests related to changed files
   - Check for hardcoded secrets before writing files
   - Validate TypeScript types after code changes
5. Have them set up a hook that solves a real problem in their workflow.
6. Discuss when NOT to use hooks — too many slow things down.

## Prompting coaching
- "Hooks are your quality safety net. They catch problems automatically so you don't have to remember to check manually."
- "Start with one hook that solves your biggest annoyance. You can always add more later."
- "If a hook is too slow, it will frustrate you. Keep hooks fast — lint one file, not the whole project."

## Quiz questions
- What is the difference between a hook and a slash command?
- When would you use a pre-tool hook vs a post-tool hook?
- What is a quality gate hook?

## Hints (only if stuck)
1. Start with a simple post-tool hook that runs a linter or formatter after file edits
2. Hooks are configured in your Claude Code settings — ask Claude to help you set one up
3. If your hook is not firing, check that the trigger event matches what you expect
