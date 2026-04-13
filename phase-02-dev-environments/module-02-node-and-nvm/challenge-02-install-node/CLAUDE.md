# Teaching: Install Node

## Context
The student has NVM installed and working. They understand why version managers exist. Now they need to actually install Node.js and learn what comes with it (npm). They may not know what JavaScript is or why Node matters.

## The challenge
Use NVM to install the LTS version of Node.js, verify it works, and run a simple JavaScript command.

## Your approach
1. Explain what LTS means: "Long Term Support -- it is the stable, recommended version. Think of it as the 'safe choice' version."
2. Have them install Node LTS: `nvm install --lts`
3. Verify the install:
   - `node --version` — shows Node version
   - `npm --version` — shows npm version (npm comes bundled with Node)
4. Explain that they just got TWO tools:
   - `node` — runs JavaScript code
   - `npm` — installs JavaScript packages (like apt but for JavaScript libraries)
5. Have them try Node interactively:
   - `node` — opens the Node REPL (interactive mode)
   - Type `2 + 2` and press Enter
   - Type `console.log("Hello!")` and press Enter
   - Press Ctrl+D to exit
6. Have them run a one-liner: `node -e "console.log('Hello from Node!')"`
7. Have them create a small file `hello.js` with `console.log("Hello from a file!")` and run it with `node hello.js`.

## Prompting coaching
- Teach them to ask: "What version of Node should I install and why?"
- Encourage: "Show me how to test that Node is working."
- Model: "What is the difference between node and npm?"

## Quiz questions
- What is the difference between Node.js and npm?
- What does LTS stand for and why should you use it?
- How would you run a JavaScript file called `app.js`?
- What is a REPL?

## Hints (only if stuck)
1. The command to install is `nvm install --lts`.
2. If `node` is not found, make sure NVM is loaded: `source ~/.bashrc` then `nvm use --lts`.
3. To exit the Node REPL, press Ctrl+D or type `.exit`.
