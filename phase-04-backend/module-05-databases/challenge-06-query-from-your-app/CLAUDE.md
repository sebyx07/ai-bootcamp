# Teaching: Query from Your App

## Context
The student can do basic CRUD with ActiveRecord. Now they need to learn more powerful queries: filtering, ordering, scopes, and avoiding common performance problems like N+1 queries.

## The challenge
Write advanced ActiveRecord queries, create model scopes, and understand eager loading.

## Your approach
1. Start in the Rails console with more advanced queries:
   ```ruby
   # Chaining queries
   Article.where("created_at > ?", 1.week.ago).order(created_at: :desc).limit(5)

   # Counting and aggregating
   Article.count
   Article.where(published: true).count

   # Querying through associations
   Article.joins(:comments).where(comments: { author: "Alice" })
   ```
2. Introduce scopes -- reusable queries defined on the model:
   ```ruby
   class Article < ApplicationRecord
     scope :recent, -> { order(created_at: :desc).limit(10) }
     scope :published, -> { where(published: true) }
   end
   ```
   Now: `Article.recent`, `Article.published`, `Article.published.recent`
3. Explain the N+1 problem:
   ```ruby
   # BAD: runs 1 query for articles + 1 query PER article for comments
   Article.all.each { |a| puts a.comments.count }

   # GOOD: runs 2 queries total
   Article.includes(:comments).each { |a| puts a.comments.count }
   ```
4. Use the controller to fetch data with scopes
5. Have them add 2-3 scopes to their Article model and use them in the controller

## Prompting coaching
- "find all articles from last week" -- practice queries
- "add a scope for published articles" -- create reusable queries
- "why is my page slow" -- learn about N+1

## Quiz questions
- What is a scope in Rails?
- What is the N+1 query problem?
- How does `includes` help with N+1?
- What does `.where("created_at > ?", 1.week.ago)` do?

## Hints (only if stuck)
1. Scopes are like saved queries -- define them once in the model, use them everywhere
2. The N+1 problem: if you load 10 articles and their comments, you might run 11 queries instead of 2
3. Use `includes(:association)` to eager load -- it loads everything in just 2 queries
