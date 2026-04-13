# Teaching: Project Conventions

## Context
The student knows CLAUDE.md exists but has never written one thoughtfully. They may have seen a basic example. They need to understand that CLAUDE.md is like onboarding documentation for an AI teammate — the better the documentation, the better the teammate performs.

## The challenge
The student will create a CLAUDE.md file for a real or practice project that captures the project's conventions so thoroughly that Claude generates code matching the existing style.

## Your approach
1. Explain what CLAUDE.md is: "It's a file I read every time you start a conversation. Whatever is in it, I treat as project context. Think of it as your way of telling me how your project works."
2. Show them what belongs in a CLAUDE.md:
   - **Tech stack**: "This is a React 18 app with TypeScript, Tailwind CSS, and Vite"
   - **Code style**: "We use functional components with hooks. No class components."
   - **Naming conventions**: "Components use PascalCase. Utility functions use camelCase. Files match their default export."
   - **Project structure**: "Components go in src/components/. API calls go in src/api/. Tests go next to the files they test."
   - **Patterns**: "We use React Query for server state. We use Zustand for client state."
   - **Things to avoid**: "Never use any. Never use console.log in production code."
3. Have them create a project (or use an existing one) and write a CLAUDE.md from scratch.
4. Test it: ask Claude to add a new component or feature and check whether it follows the conventions.
5. If it deviates, refine the CLAUDE.md and try again.

## Prompting coaching
- "Be specific in your CLAUDE.md. 'Write clean code' means nothing. 'Use early returns instead of nested ifs' means everything."
- "Your CLAUDE.md should be something a new developer could read on their first day and immediately start writing code that fits."
- "Update it over time. Every time I generate something that doesn't match your style, that's a sign your CLAUDE.md needs a new line."

## Quiz questions
- What is the purpose of a CLAUDE.md file?
- What are five things you should include in a project CLAUDE.md?
- When should you update your CLAUDE.md?

## Hints (only if stuck)
1. Start by describing your project in one sentence, then list the technologies you use
2. Look at existing code in your project and describe the patterns you see — those patterns belong in CLAUDE.md
3. Ask Claude: "Look at the code in this project and help me write a CLAUDE.md that captures its conventions"
