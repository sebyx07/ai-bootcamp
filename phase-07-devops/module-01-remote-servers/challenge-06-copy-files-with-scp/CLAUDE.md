# Teaching: Copy Files with SCP

## Context
The student can SSH into their VM, navigate around, and install software. Now they need to learn how to get files onto and off of the server. SCP (Secure Copy) uses SSH to transfer files securely. This is essential for deploying code, downloading logs, or moving configuration files.

## The challenge
Use SCP to copy files between the local machine and the VM in both directions. Practice with individual files and directories.

## Your approach
1. First, create a test file on the local machine: `echo "Hello from local" > ~/test-local.txt`
2. Explain the SCP syntax: "SCP is like cp (copy), but it works over SSH. The syntax is `scp source destination`. Either the source or destination can be a remote path: `user@host:/path/to/file`."
3. Copy local file to server:
   ```
   scp ~/test-local.txt username@vm-ip:~/
   ```
   Then SSH in and verify: `cat ~/test-local.txt`
4. Copy a file from server to local:
   - First, create a file on the server: `echo "Hello from server" > ~/test-server.txt`
   - Exit SSH, then from local: `scp username@vm-ip:~/test-server.txt ~/`
   - Verify locally: `cat ~/test-server.txt`
5. Copy a directory:
   ```
   mkdir -p ~/test-dir && echo "file1" > ~/test-dir/a.txt && echo "file2" > ~/test-dir/b.txt
   scp -r ~/test-dir username@vm-ip:~/
   ```
6. Explain the pattern:
   - Local to remote: `scp local-path user@host:remote-path`
   - Remote to local: `scp user@host:remote-path local-path`
   - The `-r` flag copies directories recursively (just like `cp -r`)
7. Mention alternatives briefly: "SCP is the simplest way to copy files. For bigger tasks, there is rsync, which is faster for syncing changes. But SCP is all you need right now."

## Prompting coaching
- "copy a file to my server" — straightforward
- "download a log file from the server" — practical use case
- "what's the difference between scp and rsync" — good curiosity question

## Quiz questions
- What does SCP stand for?
- How do you copy a directory (not just a file) with SCP?
- In the command `scp user@host:/var/log/syslog ./`, which direction is the file moving?

## Hints (only if stuck)
1. Remember: the remote side always has the `user@host:` prefix. Whichever side has that prefix is the server.
2. Use `-r` to copy directories. Without it, SCP only copies individual files.
3. If you get "Permission denied," check that you can SSH into the server without issues first — SCP uses the same authentication.
