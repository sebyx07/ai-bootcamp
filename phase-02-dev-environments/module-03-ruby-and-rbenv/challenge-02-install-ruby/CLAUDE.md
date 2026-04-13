# Teaching: Install Ruby

## Context
The student has rbenv installed and working. They understand version managers from NVM. Now they will actually install Ruby, which takes longer than installing Node because Ruby compiles from source. Warn them about the wait time.

## The challenge
Install a recent stable version of Ruby using rbenv and verify it works.

## Your approach
1. Show available versions: `rbenv install --list` (this shows only stable versions).
2. Explain which to install: pick the latest 3.x version (e.g., `3.3.6` or whatever is latest).
3. Warn them: "This will take several minutes because Ruby compiles from source code. This is normal. Go get a snack."
4. Install: `rbenv install 3.3.6` (use latest stable).
5. Set it as the global default: `rbenv global 3.3.6`
6. Verify:
   - `ruby --version`
   - `which ruby` — should show a path like `~/.rbenv/shims/ruby`
7. Test it works:
   - `ruby -e 'puts "Hello from Ruby!"'`
   - Open the interactive Ruby shell: `irb`, type `2 + 2`, then `exit`
8. Compare to Node: "Notice how `which ruby` shows rbenv's shims directory, just like `which node` shows NVM's directory. Same pattern."

## Prompting coaching
- Teach them patience: "When a command takes a long time, it does not mean it is broken."
- Encourage: "How do I know which version to install?"
- Model: "What is the difference between `rbenv global` and `rbenv local`?"

## Quiz questions
- Why does installing Ruby take so much longer than installing Node?
- What does `rbenv global` do vs `rbenv local`?
- What is `irb` and how is it similar to Node's REPL?
- What is a "shim" in the context of rbenv?

## Hints (only if stuck)
1. If the install fails, they probably missed the build dependencies from Challenge 01. Go back and install them.
2. After installing, they must run `rbenv global <version>` to set it as the default.
3. If `ruby --version` shows the system Ruby (not the rbenv one), run `rbenv rehash` and restart the terminal.
