# Teaching: Permission Denied

## Context
The student has encountered "permission denied" a few times already (probably when forgetting `sudo` with apt). This challenge dives deeper into why permissions exist, how to read them, and how to fix them properly -- not just by blindly adding `sudo` to everything.

## The challenge
Diagnose and fix permission denied errors in multiple scenarios. Learn to read permissions and understand the Linux permission model.

## Your approach

### Setting up the broken scenarios
Create a controlled directory for this exercise:
```
mkdir -p ~/permission-challenge
```

**Scenario 1: Cannot execute a script**
```
echo '#!/bin/bash' > ~/permission-challenge/hello.sh
echo 'echo "Hello World!"' >> ~/permission-challenge/hello.sh
# Do NOT chmod +x -- leave it non-executable
```
Have the student try: `~/permission-challenge/hello.sh`
They will get "Permission denied."

**Scenario 2: Cannot write to a file**
```
sudo touch ~/permission-challenge/protected.txt
sudo chown root:root ~/permission-challenge/protected.txt
sudo chmod 644 ~/permission-challenge/protected.txt
```
Have the student try: `echo "test" >> ~/permission-challenge/protected.txt`
They will get "Permission denied" because root owns it.

**Scenario 3: Cannot access a directory**
```
sudo mkdir ~/permission-challenge/secret
sudo chmod 700 ~/permission-challenge/secret
sudo chown root:root ~/permission-challenge/secret
```
Have the student try: `ls ~/permission-challenge/secret`

### Guiding the diagnosis
1. For each scenario, first ask: "What does the error tell you?"
2. Teach them to read permissions: `ls -la ~/permission-challenge/`
3. Explain the permission string: `-rwxr-xr--`
   - First character: type (- = file, d = directory)
   - Next 3: owner permissions (read, write, execute)
   - Next 3: group permissions
   - Next 3: everyone else's permissions
4. Explain ownership: every file has an owner and a group.

### Teaching the fixes
- **Scenario 1**: `chmod +x hello.sh` -- add execute permission
- **Scenario 2**: `sudo chown $USER protected.txt` -- change ownership, OR `sudo` to write as root
- **Scenario 3**: `sudo chmod 755 secret` or `sudo chown $USER secret`
- CRITICAL: Teach when NOT to use sudo. "sudo is not a magic fix. It means 'do this as the admin.' Using it carelessly can break things or create security holes."

### Cleanup
```
rm -rf ~/permission-challenge
```

## Prompting coaching
- Teach: "I get permission denied -- how do I figure out why?"
- Encourage: "Explain file permissions like I am 5 years old."
- Model: "Should I use sudo here or is there a better way?"

## Quiz questions
- What do the letters r, w, and x mean in file permissions?
- Why should you NOT just add `sudo` to every command that fails?
- What is the difference between `chmod` and `chown`?
- What does `chmod 755` mean?

## Hints (only if stuck)
1. Always start with `ls -la` to see the permissions and ownership.
2. If you own the file but cannot execute it, you need `chmod +x`.
3. If someone else owns the file, you either need `sudo` or need to change ownership with `chown`.
