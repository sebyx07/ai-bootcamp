# Teaching: Install Redis

## Context
The student just installed PostgreSQL, so they understand the concept of a database service. Redis is different: it stores data in memory (RAM) instead of on disk, making it incredibly fast but not suitable for all data. They need to understand when to use each.

## The challenge
Install Redis, connect to it, and learn basic key-value operations.

## Your approach
1. Explain Redis vs PostgreSQL: "PostgreSQL is like a filing cabinet -- it stores data permanently and you can organize it in complex ways. Redis is like a whiteboard -- it is incredibly fast to read and write, but it is meant for temporary data like caches and sessions."
2. Install Redis:
   ```
   sudo apt update
   sudo apt install -y redis-server
   ```
3. Start and check the service:
   ```
   sudo systemctl start redis-server
   sudo systemctl status redis-server
   ```
4. Connect: `redis-cli`
5. Try basic commands:
   ```
   PING           (should return PONG)
   SET name "Your Name"
   GET name
   SET counter 0
   INCR counter
   INCR counter
   GET counter
   ```
6. Show more data types:
   ```
   LPUSH colors "red"
   LPUSH colors "blue"
   LPUSH colors "green"
   LRANGE colors 0 -1
   ```
7. Show expiration (this is what makes Redis special for caching):
   ```
   SET session "abc123" EX 10
   GET session        (returns "abc123")
   # wait 10 seconds
   GET session        (returns nil -- it expired!)
   ```
8. Type `exit` to leave redis-cli.
9. Discuss when to use Redis: caching, session storage, rate limiting, real-time leaderboards, queues.

## Prompting coaching
- Teach: "When would I use Redis instead of PostgreSQL?"
- Encourage: "What does it mean that Redis stores data in memory?"
- Model: "What happens to Redis data if the server restarts?"

## Quiz questions
- What does it mean that Redis is an "in-memory" data store?
- What is the difference between Redis and PostgreSQL?
- What happens to data in Redis if the server restarts? (By default, Redis does persist to disk periodically, but it is primarily designed for speed.)
- What is a cache and why would you use Redis for one?

## Hints (only if stuck)
1. If Redis is not running: `sudo systemctl start redis-server`.
2. If `redis-cli` cannot connect, check if the service is running.
3. Redis commands are case-insensitive: `SET`, `set`, and `Set` all work.
