# Teaching: Port Already in Use

## Context
The student has run Docker containers with port mapping and started database services. They have seen ports mentioned but may not fully understand what they are. This challenge creates a real port conflict and teaches them to resolve it.

## The challenge
Encounter a "port already in use" error, find the conflicting process, and resolve the conflict.

## Your approach

### Setting up the broken scenario
1. First, explain ports with an analogy: "Think of your computer's IP address as a building's street address. Ports are like apartment numbers. Two businesses cannot operate from the same apartment."
2. Create the conflict. Start a simple server on port 3000:
   ```
   node -e "require('http').createServer((req, res) => { res.end('I am occupying port 3000'); }).listen(3000, () => console.log('Server 1 running on port 3000'))" &
   ```
3. Now ask the student to start ANOTHER server on the same port:
   ```
   node -e "require('http').createServer((req, res) => { res.end('I also want port 3000'); }).listen(3000)"
   ```
4. They will get an error: `Error: listen EADDRINUSE: address already in use :::3000`

### Guiding the diagnosis
5. Ask: "What does this error message tell you?" Let them read it.
6. Teach the diagnostic tools:
   - `lsof -i :3000` — shows which process is using port 3000
   - `ss -tlnp | grep 3000` — another way to check (ss is the modern replacement for netstat)
   - `fuser 3000/tcp` — yet another way
7. Point out the PID (process ID) in the output.
8. Explain their options:
   - **Option A**: Stop the conflicting process: `kill <PID>`
   - **Option B**: Use a different port for the new server
   - **Option C**: If `kill` does not work, `kill -9 <PID>` (force kill, last resort)

### Teaching the fix
9. Have them choose an option and execute it.
10. Verify the port is free: `lsof -i :3000` should return nothing.
11. Now start their server successfully.

### Real-world scenarios
12. Mention common real-world port conflicts:
    - PostgreSQL (5432) conflicting with a Docker PostgreSQL container
    - Two web servers both wanting port 3000 or 8080
    - A crashed process still holding a port

### Cleanup
Kill any background processes:
```
kill $(lsof -t -i :3000) 2>/dev/null
```

## Prompting coaching
- Teach: "How do I find out what is using port 3000?"
- Encourage: "I get EADDRINUSE -- walk me through fixing it."
- Model: "What is the difference between `kill` and `kill -9`?"

## Quiz questions
- What is a port and why can only one program use a specific port at a time?
- How do you find which process is using port 8080?
- What is the difference between `kill` and `kill -9`?
- Name two ways to resolve a port conflict.

## Hints (only if stuck)
1. Use `lsof -i :<port>` to see what is using the port.
2. The PID column tells you the process ID. Use `kill <PID>` to stop it.
3. If you cannot find anything with `lsof`, try `sudo lsof -i :<port>` -- some processes need root to see.
