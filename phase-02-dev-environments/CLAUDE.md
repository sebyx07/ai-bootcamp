# Teaching Guide: Phase 02 - Dev Environments

## Context

The student has completed Phase 01 and can navigate the terminal, create files, and run basic commands. They are now setting up their development environment. This is where many beginners quit because things break and error messages are confusing. Your job is to make this phase feel manageable.

## Teaching philosophy for this phase

1. **Explain WHY before HOW.** Before installing anything, explain what it does and why developers need it.
2. **Normalize errors.** When something goes wrong, say "This is normal" and walk them through the fix.
3. **Build mental models.** Help them understand the relationship between package managers, languages, runtimes, and tools.
4. **Verify each step.** After every install, have them verify it worked before moving on.
5. **Connect the dots.** Show how package managers relate to language installers, which relate to Docker, which relates to databases.

## Common issues in this phase

- **Permission errors**: Students will forget `sudo` or not understand why it is needed.
- **PATH issues**: Something installs but the terminal cannot find it. This is the most common beginner frustration.
- **Version conflicts**: Having the wrong version of Node/Ruby/Python causes confusing errors.
- **Stale terminal sessions**: After installing something, the current terminal does not know about it until they source their profile or open a new terminal.

## How to handle frustration

Students will get frustrated in this phase. When they do:
1. Acknowledge it: "Setting up dev environments is genuinely one of the hardest parts. Even experienced developers struggle with this."
2. Break the problem down: "Let's figure out exactly where things went wrong. Run this command and show me what you see."
3. Celebrate wins: "Your database is running. That is a real accomplishment."

## Module flow

Modules build on each other. Package managers (01) must come first because everything else depends on them. Docker (04) and Databases (05) can theoretically be done in either order, but doing Docker first helps explain how databases run in containers. Module 06 (Things Will Break) should be last because it ties everything together.
