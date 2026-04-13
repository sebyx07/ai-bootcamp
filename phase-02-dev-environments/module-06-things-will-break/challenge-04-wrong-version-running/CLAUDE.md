# Teaching: Wrong Version Running

## Context
The student has installed Node with NVM and Ruby with rbenv, and they know how to switch versions. But in the real world, version mismatches cause subtle bugs: code works on one version but not another. This challenge simulates that experience.

## The challenge
Encounter a situation where the wrong version of a tool is running, diagnose it, and switch to the correct version.

## Your approach

### Setting up the broken scenario
1. Create a project directory that "requires" a specific Node version:
   ```
   mkdir -p ~/version-challenge && cd ~/version-challenge
   ```
2. Create a `.nvmrc` file specifying an older version:
   ```
   echo "18" > ~/version-challenge/.nvmrc
   ```
3. Install Node 18 if not already: `nvm install 18`
4. Switch to a DIFFERENT version: `nvm use node` (uses latest)
5. Create a JavaScript file that uses a feature only available in newer Node:
   ```javascript
   // app.js -- uses Array.groupBy which is available in Node 21+
   // but we will simulate this with a version check
   const version = process.version;
   const major = parseInt(version.slice(1).split('.')[0]);
   if (major < 18) {
     console.error(`ERROR: This project requires Node 18+, but you are running ${version}`);
     process.exit(1);
   }
   console.log(`SUCCESS: Running Node ${version} -- compatible!`);
   ```
   Actually, let's make the scenario more tangible. Change the `.nvmrc` to require Node 20:
   ```
   echo "20" > ~/version-challenge/.nvmrc
   ```
6. Switch to Node 18: `nvm use 18`
7. Update the script to require Node 20+.

### Presenting the problem
8. Tell the student: "A teammate says this project requires Node 20 but your code is failing. Can you figure out what is wrong?"
9. Have them run: `node ~/version-challenge/app.js`
10. They should see the version mismatch error.

### Guiding the diagnosis
11. Ask: "What does the error say? What version is running?"
12. Have them check:
    - `node --version` — what version am I running?
    - `which node` — where is it coming from?
    - `cat ~/version-challenge/.nvmrc` — what version does the project want?
13. Teach the pattern: "Always check `<tool> --version` when something is not working. Version mismatches are one of the most common sources of bugs."

### Teaching the fix
14. Have them switch: `cd ~/version-challenge && nvm use`
15. This reads `.nvmrc` and switches to the right version.
16. Run the script again -- it should work.
17. Also show: `nvm use 20` as the explicit version of the same command.

### Real-world connection
18. Explain: "This is why `.nvmrc` files exist. They are checked into git so everyone on a team uses the same Node version. Same concept for `.ruby-version` with rbenv."

### Cleanup
```
rm -rf ~/version-challenge
nvm use default
```

## Prompting coaching
- Teach: "My code works on my teammate's machine but not mine. What should I check?"
- Encourage: "How do I make sure everyone on my team uses the same Node version?"
- Model: "What is a .nvmrc file and why does it matter?"

## Quiz questions
- How do you check which version of Node is currently active?
- What does a `.nvmrc` file do?
- Why might code work on one version of Node but fail on another?
- How does `nvm use` (with no version) know which version to switch to?

## Hints (only if stuck)
1. Check what version is running: `node --version`.
2. Check what version the project wants: look for `.nvmrc` or `package.json` engines field.
3. Switch versions with `nvm use <version>` or just `nvm use` if there is a `.nvmrc` file.
