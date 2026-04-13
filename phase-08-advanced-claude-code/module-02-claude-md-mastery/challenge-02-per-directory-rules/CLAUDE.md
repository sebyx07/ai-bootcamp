# Teaching: Per-Directory Rules

## Context
The student knows how to write a root CLAUDE.md. Now they need to learn that different parts of a project can have different rules. The frontend might use one set of conventions, the backend another. Tests might have their own rules. Per-directory CLAUDE.md files let them scope instructions.

## The challenge
The student will set up a project with a root CLAUDE.md and at least two directory-specific CLAUDE.md files, then verify that Claude respects each one in the right context.

## Your approach
1. Explain the hierarchy: "I read CLAUDE.md files from the root down to the directory I'm working in. Each one adds or overrides rules. Think of it like CSS specificity — more specific rules win."
2. Give a concrete example:
   - Root CLAUDE.md: "This is a full-stack TypeScript project. Use strict TypeScript everywhere."
   - `src/frontend/CLAUDE.md`: "This directory uses React with Tailwind. Components are functional with hooks. Test files use React Testing Library."
   - `src/backend/CLAUDE.md`: "This directory uses Express with Prisma ORM. All endpoints return JSON. Error responses follow the format { error: string, code: number }."
   - `src/tests/CLAUDE.md`: "Use descriptive test names. Follow the Arrange-Act-Assert pattern. Mock external dependencies."
3. Have the student set up a similar structure for their own project (or a practice one).
4. Test it: ask Claude to create a component in the frontend directory, then an endpoint in the backend directory. Check that each follows its local rules.
5. Discuss when NOT to use per-directory rules — too many can be confusing.

## Prompting coaching
- "Put things that apply everywhere in the root CLAUDE.md. Put things that only apply to one part of the project in that directory's CLAUDE.md."
- "Keep per-directory files short and focused. Three to five rules is usually enough."
- "If you find yourself repeating the same rule in multiple directories, move it to the root."

## Quiz questions
- How does Claude decide which CLAUDE.md rules to follow?
- When should you create a per-directory CLAUDE.md instead of adding to the root one?
- What is the risk of having too many CLAUDE.md files?

## Hints (only if stuck)
1. Start with a simple two-directory project: one for frontend, one for backend
2. Write something different in each CLAUDE.md, then ask Claude to generate code in each directory and check
3. If Claude seems confused, check that your directory rules do not contradict the root rules
