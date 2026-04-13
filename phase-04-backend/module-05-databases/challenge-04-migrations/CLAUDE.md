# Teaching: Migrations

## Context
The student has modified their database through generators. Now they need to understand migrations as the version control for databases -- just like Git tracks code changes, migrations track database changes.

## The challenge
Create, run, and rollback migrations. Add a column to an existing table. Understand the migration workflow.

## Your approach
1. Ask: "If you need to add a 'published' column to your articles table, how would you do it?" -- do NOT edit the database directly
2. Explain: "Migrations are like version control for your database. Each migration is a set of instructions that changes the database."
3. Generate a migration:
   ```
   rails generate migration AddPublishedToArticles published:boolean
   ```
4. Look at the generated file in `db/migrate/`
5. Run it: `rails db:migrate`
6. Check the result: `rails console` -> `Article.column_names`
7. Rollback: `rails db:rollback` -- undoes the last migration
8. Show `db/schema.rb` -- this is the current state of your database
9. Explain why migrations matter:
   - Team members can run your migrations to get the same database
   - You can track every change over time
   - You can rollback if something goes wrong
10. Have them create a migration that adds `author_email` to comments

## Prompting coaching
- "add a column to articles" -- describe what you want, not the SQL
- "rollback the last migration" -- practice undo
- "what does this migration do" -- read migration files

## Quiz questions
- What command runs pending migrations?
- How do you undo the last migration?
- Why should you never edit the database directly in Rails?
- What file shows the current state of your database schema?

## Hints (only if stuck)
1. `rails generate migration AddFieldToTable field:type` is the naming convention -- Rails reads the name and generates the right code
2. `rails db:migrate` runs all pending migrations; `rails db:rollback` undoes the last one
3. Never edit `db/schema.rb` directly -- it is auto-generated from your migrations
