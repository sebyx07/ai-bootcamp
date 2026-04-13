# Teaching: Command Not Found

## Context
The student has installed many tools throughout this phase. "Command not found" is the error they will see most often in their career. This challenge intentionally breaks something so they can practice diagnosing it. You must simulate the broken scenario, then guide them through fixing it WITHOUT just giving them the answer.

## The challenge
Diagnose and fix a "command not found" error. The student should learn the systematic approach to debugging this error.

## Your approach

### Setting up the broken scenario
1. Choose ONE of these scenarios (pick based on what the student has installed):

   **Scenario A: Node goes missing**
   - Temporarily break Node by switching to a nonexistent NVM alias:
     ```
     nvm alias default nonexistent 2>/dev/null
     nvm deactivate
     ```
   - Now `node --version` will say "command not found"

   **Scenario B: A tool was never installed**
   - Ask the student to run `python3 --version` or `go version` -- something they have not installed yet
   - This teaches them: "command not found" sometimes just means "you need to install it"

   **Scenario C: Typo in command name**
   - Have them type `ndoe --version` or `dockre ps`
   - Teaches them to check spelling first

2. Present the error WITHOUT explaining it: "Try running `node --version`. What do you see?"

### Guiding the diagnosis (do NOT give answers immediately)
3. Ask them: "What does this error message tell you?" Let them think.
4. Teach the diagnostic checklist:
   - **Step 1: Did you spell it right?** Check for typos.
   - **Step 2: Is it installed?** Use `which <command>` or `command -v <command>`.
   - **Step 3: Is it in your PATH?** Run `echo $PATH` and check if the tool's directory is listed.
   - **Step 4: Did you open a new terminal?** Some installs require a shell restart.
   - **Step 5: Did the install actually succeed?** Go back and check.
5. Walk them through each step for the specific scenario.

### Fixing it
6. Once they identify the problem, let THEM propose the fix. Ask: "What do you think we should do?"
7. After fixing, verify it works.
8. Restore everything to working state.

## Prompting coaching
- Teach: "I get 'command not found' -- what should I check first?"
- Encourage: "Walk me through how to debug 'command not found' step by step."
- Model: "What does `which` do and how does it help?"

## Quiz questions
- Name 4 reasons you might get "command not found."
- What does the `which` command do?
- If `which node` returns nothing, what does that tell you?
- What is the first thing you should check when you get "command not found"?

## Hints (only if stuck)
1. Start simple: did you spell the command correctly?
2. Use `which <command>` to see if the system knows where it is.
3. Check if the tool is installed and its directory is in your PATH with `echo $PATH`.
