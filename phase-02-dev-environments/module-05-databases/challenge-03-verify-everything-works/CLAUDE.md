# Teaching: Verify Everything Works

## Context
The student has installed many tools across this entire phase. Before moving on, they need to verify everything is working and build a mental map of their development environment. This challenge is also a great opportunity to teach them a practical skill: writing a verification script.

## The challenge
Create a shell script that checks all installed tools and services, then run it to verify the complete dev environment.

## Your approach
1. Start by asking: "Can you name all the tools we have installed in this phase?" See how many they remember.
2. Walk through manual checks first:
   ```
   apt --version
   nvm --version
   node --version
   npm --version
   ruby --version
   gem --version
   bundle --version
   docker --version
   docker compose version
   psql --version
   redis-cli --version
   ```
3. Check services:
   ```
   sudo systemctl status postgresql
   sudo systemctl status redis-server
   ```
4. Now teach them to write a verification script (`check-env.sh`):
   ```bash
   #!/bin/bash
   echo "=== Development Environment Check ==="
   echo ""

   check_command() {
     if command -v "$1" &> /dev/null; then
       echo "[OK] $1: $($1 --version 2>&1 | head -1)"
     else
       echo "[MISSING] $1 is not installed"
     fi
   }

   check_command node
   check_command npm
   check_command ruby
   check_command gem
   check_command docker
   check_command psql
   check_command redis-cli

   echo ""
   echo "=== Services ==="
   if systemctl is-active --quiet postgresql; then
     echo "[RUNNING] PostgreSQL"
   else
     echo "[STOPPED] PostgreSQL"
   fi

   if systemctl is-active --quiet redis-server; then
     echo "[RUNNING] Redis"
   else
     echo "[STOPPED] Redis"
   fi

   echo ""
   echo "=== Environment Check Complete ==="
   ```
5. Make it executable: `chmod +x check-env.sh`
6. Run it: `./check-env.sh`
7. Fix anything that shows as MISSING or STOPPED.
8. Celebrate: "You now have a professional development environment. This is genuinely impressive."

## Prompting coaching
- Teach: "How do I check if all my tools are installed and working?"
- Encourage: "Can you help me write a script that checks everything at once?"
- Model: "What command tells me if a service is running?"

## Quiz questions
- How do you check if a command-line tool is installed?
- What is the difference between a tool being installed and a service running?
- Why might `which node` show a path but `node --version` fail?
- What does `chmod +x` do and why do you need it?

## Hints (only if stuck)
1. If a tool is missing, go back to the module where it was installed and redo the install.
2. If a service is not running, start it with `sudo systemctl start <service>`.
3. NVM commands only work in bash (not in plain sh scripts). Check NVM separately if it does not show up.
