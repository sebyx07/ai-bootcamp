# Teaching: Built-in Skills

## Context
The student has used Claude Code conversationally but has not explored slash commands or skills. They may have seen /help or /clear but have not thought of them as a system. They need to understand that skills are reusable, pre-configured prompts that activate specific Claude capabilities.

## The challenge
The student will explore and use built-in slash commands, understand what skills are under the hood, and start thinking about which workflows could benefit from dedicated commands.

## Your approach
1. Explain what skills are: "Skills are like saved workflows. Instead of typing a long prompt every time, you type a short command like /review and I know exactly what to do. Think of them as shortcuts."
2. Walk them through discovery:
   - Type `/help` to see available commands
   - Explore key built-in commands:
     - `/plan` — creates an implementation plan before coding
     - `/review` — reviews code for issues
     - `/clear` — clears the conversation context
     - `/compact` — summarizes the conversation to free up context
3. Have them use each one on a real task:
   - Use `/plan` before building something
   - Use `/review` after generating code
   - Use `/compact` during a long conversation
4. Explain the difference between a skill and a regular prompt: "A skill has pre-configured instructions that shape how I respond. When you say /review, I don't just read the code — I follow a specific checklist."
5. Ask them to identify three workflows in their own work that could benefit from a dedicated command. (This sets up the next challenge.)

## Prompting coaching
- "Slash commands are faster than typing the same instructions over and over."
- "If you find yourself typing the same kind of prompt repeatedly, that is a sign it should be a slash command."
- "You don't have to memorize all commands. Just remember /help exists."

## Quiz questions
- What is a Claude Code skill?
- How do you see all available slash commands?
- What is the difference between typing "review my code" and using /review?

## Hints (only if stuck)
1. Start with /help to see what is available
2. Try /plan on any task — even a simple one — to see how it changes the workflow
3. If a command does not seem useful now, that is fine — you will use it later when your projects are bigger
