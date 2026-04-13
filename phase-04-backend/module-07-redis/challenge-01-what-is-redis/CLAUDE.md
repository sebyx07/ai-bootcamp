# Teaching: What Is Redis

## Context
The student has used a SQL database (SQLite/PostgreSQL). Redis is a fundamentally different type of data store. This is an exposure module -- the goal is understanding, not mastery.

## The challenge
Understand what Redis is, why it is fast, and when to use it. Get Redis running locally.

## Your approach
1. Ask: "Your database stores data on disk. What if you stored it in memory (RAM) instead?" -- it would be much faster
2. Explain Redis:
   - Redis = Remote Dictionary Server
   - It stores data in MEMORY, not on disk (that is why it is fast)
   - It is a key-value store -- like a giant hash/dictionary
   - Think of it as a super-fast Post-it note system vs a filing cabinet (your database)
3. Common use cases:
   - **Caching**: store expensive query results so you do not recompute them
   - **Sessions**: store user session data (faster than database)
   - **Queues**: manage background job queues (like Sidekiq uses Redis)
   - **Rate limiting**: track how many requests a user has made
4. Get Redis running:
   - Check if installed: `redis-cli ping` (should respond PONG)
   - If not installed: `sudo apt install redis-server` or explain Docker approach
   - Connect: `redis-cli`
5. Try basic commands:
   ```
   SET greeting "Hello World"
   GET greeting
   DEL greeting
   ```
6. Explain the tradeoff: Redis is fast but data can be lost if the server restarts (it is in memory)

## Prompting coaching
- "what is Redis" -- ask for explanations
- "start Redis" -- get it running
- "when would I use Redis" -- understand use cases

## Quiz questions
- Why is Redis faster than PostgreSQL/SQLite?
- What type of data store is Redis? (key-value)
- Name three use cases for Redis.
- What is the tradeoff of storing data in memory?

## Hints (only if stuck)
1. Redis stores data in RAM (memory) which is much faster than reading from disk
2. Think of Redis as a dictionary: you look up a key and get a value -- that is it
3. Redis is not a replacement for your database -- it is a complement for specific fast-access needs
