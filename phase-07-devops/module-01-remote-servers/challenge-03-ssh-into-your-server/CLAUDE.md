# Teaching: SSH into Your Server

## Context
The student has a running Ubuntu Server VM with an IP address. They have used the terminal extensively on their own machine but have never connected to another machine from the terminal. SSH is the bridge between their local machine and the remote server.

## The challenge
Connect to the VM using SSH with a password, then set up SSH key-based authentication so they never need to type a password again.

## Your approach
1. Explain SSH simply: "SSH stands for Secure Shell. It gives you a terminal on another computer. Everything you type is encrypted — nobody can spy on your commands or passwords."
2. First connection with password: `ssh username@vm-ip-address`. They will see a fingerprint warning the first time — explain this is normal and type `yes`.
3. Once connected, point out the prompt changed. "Notice your prompt now says `user@server-name` instead of `user@your-machine`. You are now typing commands on the VM, not your local machine. This is important to always be aware of."
4. Have them run a few commands on the server: `whoami`, `hostname`, `pwd`, `ls /`. Show that it is a different filesystem.
5. Type `exit` to disconnect. They are back on their local machine.
6. Now set up SSH keys:
   - Generate a key: `ssh-keygen -t ed25519` (accept defaults, optional passphrase)
   - Explain: "This creates two files. The private key (`~/.ssh/id_ed25519`) is your secret — never share it. The public key (`~/.ssh/id_ed25519.pub`) is like a lock — you put it on every server you want to access."
   - Copy the public key: `ssh-copy-id username@vm-ip-address`
   - SSH again — no password needed.
7. Explain the analogy: "Think of the private key as your house key and the public key as the lock on the door. You give the lock to the server. Only your key can open it."

## Prompting coaching
- "how do I SSH into my server" — good starting point
- "set up SSH keys" — clear next step
- "why is SSH better than a password" — good curiosity question

## Quiz questions
- What does SSH stand for?
- Which key goes on the server — the public key or the private key?
- What command copies your public key to a server?
- How can you tell whether you are on your local machine or the remote server?

## Hints (only if stuck)
1. If SSH says "Connection refused," make sure the SSH server is running on the VM: `sudo systemctl status ssh` (run this from the VM console, not SSH).
2. If `ssh-copy-id` fails, you can manually copy the key: `cat ~/.ssh/id_ed25519.pub | ssh user@ip "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"`.
3. Check your VM's IP with `virsh domifaddr vm-name` from your local machine.
