# Teaching: Caching in Your App

## Context
The student knows Redis commands. Now they connect it to their Rails app and use it for a real purpose: caching. This is a practical exposure to how Redis is used in production apps.

## The challenge
Add Redis caching to the blog app. Cache the article count or the list of recent articles.

## Your approach
1. Ask: "If your homepage shows the 10 most recent articles, and you get 1000 visitors per minute, how many database queries is that?" -- 1000 queries for the same data
2. Explain caching: store the result of an expensive operation so you do not repeat it
3. Set up Redis in Rails:
   - Add to Gemfile: `gem 'redis'`
   - Run `bundle install`
   - Configure in `config/environments/development.rb`:
     ```ruby
     config.cache_store = :redis_cache_store, { url: "redis://localhost:6379/0" }
     ```
4. Use Rails caching:
   ```ruby
   # In the controller
   @articles = Rails.cache.fetch("recent_articles", expires_in: 5.minutes) do
     Article.order(created_at: :desc).limit(10).to_a
   end
   ```
5. Explain how `fetch` works:
   - First call: runs the block, stores result in Redis, returns it
   - Subsequent calls: returns the cached result (does not hit the database)
   - After 5 minutes: cache expires, next call runs the block again
6. Show how to clear the cache: `Rails.cache.clear`
7. Have them add caching and observe the difference in the Rails server logs (fewer SQL queries)

## Prompting coaching
- "add caching to my articles page" -- describe what you want
- "clear the cache" -- manage cached data
- "how do I know if caching is working" -- verify with logs

## Quiz questions
- What does caching mean?
- What does `expires_in: 5.minutes` do?
- What happens when cached data expires?
- When should you NOT cache data?

## Hints (only if stuck)
1. `Rails.cache.fetch("key", expires_in: time) { expensive_operation }` is the main pattern
2. Check your Rails server logs -- if caching works, you will see fewer SQL queries on repeated page loads
3. Do not cache data that changes every request (like a user's cart) -- cache data that is the same for many users
