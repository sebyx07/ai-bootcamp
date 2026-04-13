# Teaching: Install NVM

## Context
The student knows how to use apt to install packages. Now they are learning that some tools are better installed a different way. NVM is installed via a shell script, not apt, which may confuse them. They need to understand why: apt's version of Node is often outdated, and NVM gives you control over which version you use.

## The challenge
Install NVM using the official install script from GitHub and verify it is working.

## Your approach
1. First, ask: "Do you know what Node.js is? Have you heard of JavaScript?" -- gauge their familiarity.
2. Explain: "Node.js lets you run JavaScript outside a web browser. We are going to install NVM first, which is a manager that lets us install any version of Node we want."
3. Explain why NOT to use `apt install nodejs`:
   - The apt version is often out of date
   - You cannot easily switch between versions
   - NVM installs Node in your home directory (no sudo needed)
4. Walk them through the install:
   - Install prerequisites: `sudo apt install curl`
   - Run the NVM install script: `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash`
   - Explain what this command does (downloads a script and runs it)
   - Source the shell profile: `source ~/.bashrc` (or open a new terminal)
5. Verify: `nvm --version`
6. If it does not work, check that the NVM lines were added to `~/.bashrc`.

## Prompting coaching
- Teach them to ask: "What does this command do step by step?" before running piped curl commands.
- Encourage them to say: "I ran the command but nvm is not found" -- this is the most common issue and they need to learn to report it clearly.

## Quiz questions
- Why do we use NVM instead of installing Node directly with apt?
- What does the `curl -o- <url> | bash` pattern do? Is it safe?
- What file did NVM modify when it installed? Why?
- If you open a new terminal tab, will NVM still work? Why?

## Hints (only if stuck)
1. If `nvm` is not found after installing, they need to restart their terminal or run `source ~/.bashrc`.
2. Check that `~/.bashrc` contains lines starting with `export NVM_DIR`.
3. The full install command is: `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash`
