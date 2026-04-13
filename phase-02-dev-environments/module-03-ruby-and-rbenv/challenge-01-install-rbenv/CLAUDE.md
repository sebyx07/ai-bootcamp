# Teaching: Install rbenv

## Context
The student has already installed NVM for Node.js, so they understand the concept of version managers. Now they are learning that Ruby has its own version manager called rbenv. Emphasize the pattern: most programming languages have a version manager, and they all work similarly.

## The challenge
Install rbenv and its ruby-build plugin so they can install Ruby versions.

## Your approach
1. Start by connecting to what they know: "Remember how NVM lets you install different versions of Node? rbenv does the same thing for Ruby."
2. Install the build dependencies first:
   ```
   sudo apt install -y build-essential libssl-dev libreadline-dev zlib1g-dev libsqlite3-dev libyaml-dev
   ```
   Explain: "Ruby needs to be compiled from source code. These are the tools needed to build it."
3. Install rbenv using the official installer:
   ```
   curl -fsSL https://rbenv.org/install.sh | bash
   ```
4. Add rbenv to their shell profile if not done automatically:
   ```
   echo 'eval "$(~/.rbenv/bin/rbenv init - bash)"' >> ~/.bashrc
   source ~/.bashrc
   ```
5. Verify: `rbenv --version`
6. Check that ruby-build is also installed: `rbenv install --list` should show available versions.

## Prompting coaching
- Reinforce the pattern: "How is this similar to how we installed NVM?"
- Teach them to ask: "What dependencies do I need before installing?"
- Encourage: "What would I search for if I wanted to find a version manager for Python?"

## Quiz questions
- What is the pattern that NVM and rbenv share?
- Why does Ruby need build tools (build-essential, libssl-dev, etc.) but Node did not?
- What is ruby-build and why do we need it alongside rbenv?

## Hints (only if stuck)
1. If `rbenv` is not found, they need to add it to their PATH and restart the shell.
2. The build dependencies are essential -- if they skip them, Ruby will fail to compile later.
3. Check `~/.bashrc` for the rbenv init line.
