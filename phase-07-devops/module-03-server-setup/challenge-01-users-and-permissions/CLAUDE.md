# Teaching: Users and Permissions

## Context
The student has been using `sudo` without fully understanding it. They have seen permission errors but may not know why they happen. On a real server, proper user management and permissions are a security requirement — you never run applications as root, and every file should have the minimum permissions necessary.

## The challenge
Create a new user on the VM, understand the Linux permission system, and practice changing ownership and permissions on files.

## Your approach
1. Explain why this matters: "On your personal machine, you are the only user and you can do whatever you want. On a server, you need to be careful. Running everything as root is like leaving your front door wide open — convenient but dangerous."
2. Show current users: `cat /etc/passwd | grep -v nologin | grep -v false` — real users who can log in.
3. Create a new user:
   ```
   sudo adduser deploy
   ```
   Walk through the prompts (password, full name — they can skip the rest).
4. Add the user to the sudo group: `sudo usermod -aG sudo deploy`
5. Test the new user: `su - deploy`, then `whoami`, then `exit`.
6. Teach permissions with `ls -la`:
   - The string `drwxr-xr-x` means: directory (d), owner can read/write/execute (rwx), group can read/execute (r-x), others can read/execute (r-x).
   - Break it down: `rwx | r-x | r-x` = owner | group | others
7. Practice changing permissions:
   - Create a test file: `touch ~/testfile`
   - View permissions: `ls -la ~/testfile`
   - Make it executable: `chmod +x ~/testfile`
   - Remove all permissions for others: `chmod o-rwx ~/testfile`
   - Set specific permissions with numbers: `chmod 644 ~/testfile` (owner: rw, group: r, others: r)
8. Practice changing ownership:
   - `sudo chown deploy:deploy ~/testfile` — change owner and group
9. Explain the principle of least privilege: "Only give permissions that are needed. A web server should not be able to read your SSH keys. A database should not be able to modify web files."

## Prompting coaching
- "create a new user on the server" — direct and actionable
- "explain linux permissions" — good for conceptual understanding
- "what does 755 mean" — focused question about permission numbers

## Quiz questions
- What does `sudo` stand for and what does it do?
- In the permission string `rw-r--r--`, what can the owner do? What can others do?
- Why should you not run your web application as root?
- What command changes the owner of a file?

## Hints (only if stuck)
1. Permission numbers: r=4, w=2, x=1. Add them up: rwx=7, r-x=5, r--=4. So `chmod 755` means owner=rwx, group=r-x, others=r-x.
2. If you lock yourself out of a file, use `sudo` to fix the permissions.
3. To see which groups a user belongs to: `groups username`.
