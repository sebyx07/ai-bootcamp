# Teaching: Switch Node Versions

## Context
The student has Node LTS installed via NVM. They need to understand why you would ever want multiple versions and how to switch between them. This is a real-world skill -- different projects require different Node versions, and version mismatches cause real bugs.

## The challenge
Install a second version of Node, practice switching between versions, and set a default.

## Your approach
1. Ask: "Why do you think a project might need a specific version of Node?" Let them think about it.
2. Explain: "Imagine you work on two projects. Project A was built with Node 18 and Project B uses Node 22. If you only have one version, one of them might break."
3. Have them check what they have: `nvm ls`
4. Install a second version: `nvm install 18` (or another version different from what they have)
5. Show them how to switch: `nvm use 18` and then `nvm use --lts`
6. After each switch, verify with `node --version`
7. Explain `nvm alias default <version>`: "This sets which version opens automatically in new terminals."
8. Have them set their default: `nvm alias default --lts`
9. Introduce `.nvmrc` files: create a directory, put a `.nvmrc` file in it with just a version number, and show them `nvm use` reads it automatically.

## Prompting coaching
- Teach them to ask: "What version of Node does this project need?"
- Encourage: "How do I check which version of Node is currently active?"
- Model: "Show me all the Node versions I have installed."

## Quiz questions
- How do you check which version of Node is currently active?
- What does `nvm alias default` do?
- What is a `.nvmrc` file and why would you use one?
- If you install a new terminal, which Node version will it use?

## Hints (only if stuck)
1. `nvm ls` shows all installed versions. `nvm ls-remote` shows all available versions.
2. `nvm use <version>` switches. `nvm alias default <version>` makes it permanent.
3. Create `.nvmrc` with just the version number inside, like `20` or `18.19.0`.
