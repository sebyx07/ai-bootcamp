# Teaching: Key-Value Operations

## Context
The student has Redis running and has done basic SET/GET. Now they explore more data types and the TTL feature that makes Redis powerful for caching.

## The challenge
Practice Redis commands including strings, lists, hashes, and key expiration.

## Your approach
1. Open `redis-cli` and practice:
2. **String operations:**
   ```
   SET user:1:name "Alice"
   GET user:1:name
   INCR page_views          # increment a counter
   DECR page_views          # decrement
   ```
3. **Expiration (TTL):**
   ```
   SET session:abc123 "user_data" EX 3600   # expires in 1 hour
   TTL session:abc123                        # seconds remaining
   ```
4. **Lists:**
   ```
   LPUSH queue:emails "email1"
   LPUSH queue:emails "email2"
   LRANGE queue:emails 0 -1        # get all items
   RPOP queue:emails                # remove from right
   ```
5. **Hashes:**
   ```
   HSET user:1 name "Alice" age "25" email "alice@example.com"
   HGET user:1 name
   HGETALL user:1
   ```
6. Key naming convention: use colons for namespacing (`user:1:name`, `session:abc123`)
7. Compare to what they know:
   - Redis strings: like a simple variable
   - Redis lists: like an array
   - Redis hashes: like a Ruby hash or JS object
8. Explain: TTL (Time To Live) is what makes Redis perfect for caching -- data automatically disappears after a set time

## Prompting coaching
- "store a user in Redis" -- practice hash operations
- "set a key that expires in 5 minutes" -- practice TTL
- "what data types does Redis support" -- explore features

## Quiz questions
- What does TTL stand for and what does it do?
- What command gets all fields from a Redis hash?
- How is a Redis list different from a SQL table?
- What happens to a key when its TTL reaches 0?

## Hints (only if stuck)
1. `SET key value EX seconds` sets a key that automatically deletes after the given seconds
2. `HSET` is for hashes (multiple fields) while `SET` is for simple strings
3. Use `KEYS *` to see all keys (be careful in production -- use `SCAN` instead)
