# Teaching: Disk, Memory, CPU

## Context
The student can do a basic health check. Now they need to go deeper into system resources. The three things that cause most server problems: running out of disk space, running out of memory, and CPU overload. Learning to check these quickly is essential server administration.

## The challenge
Learn to use df, free, and htop to monitor system resources. Understand what the numbers mean and when to worry.

## Your approach
1. Start with disk space — `df -h`:
   - Run it and explain each column: Filesystem, Size, Used, Available, Use%, Mounted on
   - Focus on the `/` filesystem — that is the main disk
   - Explain the `-h` flag: "human-readable" — shows GB/MB instead of bytes
   - Warning threshold: "If any filesystem is over 90% full, you need to act."
   - Show `du -sh /var/log` to check how much space a specific directory uses
   - Show `du -sh /* 2>/dev/null | sort -hr | head -10` to find the biggest directories

2. Memory — `free -h`:
   - Run it and explain: total, used, free, available
   - The important number is "available" not "free." Linux uses unused memory for caching, which is good.
   - Explain swap: "Swap is disk space used as fake RAM. If the server is using a lot of swap, it means it is running low on real memory and will be slow."
   - Warning: "If available memory is very low and swap is being used heavily, your server needs more RAM or something is using too much."

3. CPU and processes — `htop`:
   - Install it if not already: `sudo apt install -y htop`
   - Run `htop` and walk through the interface:
     - Top bars: CPU usage for each core, memory bar
     - Process list: PID, USER, CPU%, MEM%, command
   - Teach sorting: press `F6` or `>` to sort by CPU% or MEM%
   - Teach searching: press `F3` or `/` to search for a process
   - Teach killing: select a process, press `F9`, choose signal 15 (TERM)
   - Press `q` to quit
   - Explain: "htop is your dashboard. When the server is slow, this tells you why."

4. Give them a challenge: "Find out which process is using the most memory on your server."

5. Briefly mention `top` (the older version of htop) — they may see it on servers where htop is not installed.

## Prompting coaching
- "check disk space on my server" — leads to df -h
- "is my server running out of memory" — leads to free -h
- "what is using the most CPU" — leads to htop
- "my server is slow, help me find why" — great debugging prompt

## Quiz questions
- What does `df -h` show you?
- What is the difference between "free" and "available" memory?
- What is swap, and why is heavy swap usage a bad sign?
- How do you sort processes by memory usage in htop?
- At what disk usage percentage should you start worrying?

## Hints (only if stuck)
1. Remember `-h` means "human-readable." Use it with both `df` and `free`.
2. In htop, press `q` to quit. Do not close the terminal — just press `q`.
3. If htop is not installed, use `top` — it shows similar information but is less user-friendly.
