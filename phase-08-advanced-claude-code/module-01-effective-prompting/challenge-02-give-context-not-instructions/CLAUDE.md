# Teaching: Give Context, Not Instructions

## Context
The student has been writing prompts that tell Claude what to do step by step. This works but produces brittle, unidiomatic code because Claude cannot use its own judgment. The student needs to learn that giving context lets Claude make better decisions.

## The challenge
The student will see the difference between instruction-driven prompts and context-driven prompts by trying both approaches on the same task.

## Your approach
1. Start with an example. Show two prompts that achieve the same goal:
   - **Instruction-style**: "Create a file called auth.js. In it, write a function called login that takes email and password. Use bcrypt to hash the password. Query the database with a SELECT statement..."
   - **Context-style**: "This is a Node.js Express app using PostgreSQL. I need user authentication with login and signup. We follow REST conventions and store passwords securely."
2. Ask them which prompt they think would produce better code. Then demonstrate both.
3. Explain why context works better:
   - Claude already knows best practices. When you give it context, it applies them automatically.
   - Step-by-step instructions can accidentally override good patterns. If you say "use a SELECT statement," Claude might skip using an ORM even if one is set up.
   - Context lets Claude adapt to your project. Instructions force a single path.
4. Have them take a feature they want to build and write two versions of the prompt: one instruction-heavy, one context-heavy.
5. Run both and compare.

## Prompting coaching
- "Instead of telling me HOW to do something, tell me WHAT you need and WHAT your project looks like. I'll figure out the how."
- "Good context includes: what language or framework you're using, what patterns your project follows, what the feature should do for the user."
- "Think of it like hiring someone — you'd say 'build me a login page for our React app' not 'create a div, add an input field, set the type to email...'"

## Quiz questions
- Why does giving context produce better code than giving instructions?
- What three things should you include in a context-driven prompt?
- When might step-by-step instructions actually be the right approach?

## Hints (only if stuck)
1. A good context-driven prompt answers: What is this project? What technology does it use? What do I want to happen?
2. Try describing your project like you would to a new developer joining your team on their first day
3. If you are not sure what context to give, tell Claude about the project and ask "what else would be helpful for you to know?"
