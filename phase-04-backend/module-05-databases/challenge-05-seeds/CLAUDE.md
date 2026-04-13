# Teaching: Seeds

## Context
The student has been creating data manually in the console or through forms. Seed files let you populate the database with sample data automatically -- essential for development and demos.

## The challenge
Write a seed file that creates sample articles with comments, and learn the seed workflow.

## Your approach
1. Ask: "Every time you reset your database, all your test data is gone. How would you fix that?"
2. Open `db/seeds.rb` and write seed data together:
   ```ruby
   # Clear existing data
   Comment.destroy_all
   Article.destroy_all

   # Create articles
   10.times do |i|
     article = Article.create!(
       title: "Article #{i + 1}",
       body: "This is the body of article #{i + 1}. It has interesting content."
     )

     # Create comments for each article
     3.times do |j|
       article.comments.create!(
         author: "Commenter #{j + 1}",
         body: "This is comment #{j + 1} on article #{i + 1}."
       )
     end
   end

   puts "Created #{Article.count} articles and #{Comment.count} comments"
   ```
3. Run seeds: `rails db:seed`
4. Verify in the console: `Article.count`, `Comment.count`
5. Show the full reset workflow: `rails db:reset` (drop + create + migrate + seed)
6. Explain when seeds are useful:
   - Starting fresh in development
   - Setting up a new team member's database
   - Creating demo data
7. Have them customize the seed data with more realistic content

## Prompting coaching
- "create seed data for my blog" -- describe what you want
- "add more realistic content" -- improve seeds
- "reset my database" -- learn the reset workflow

## Quiz questions
- What file contains seed data in Rails?
- What command runs the seed file?
- Why do we call `destroy_all` at the beginning of the seed file?
- What does `rails db:reset` do?

## Hints (only if stuck)
1. Seeds live in `db/seeds.rb` -- run them with `rails db:seed`
2. Use `create!` (with the bang) instead of `create` -- it raises an error if validation fails, so you catch problems early
3. `rails db:reset` drops the database, recreates it, runs migrations, and runs seeds -- a clean start
