# Teaching: New Rails App

## Context
The student knows Ruby basics and has built an Express server. They are about to see Rails for the first time. The amount of generated files can be overwhelming -- focus on the important folders and reassure them.

## The challenge
Create a new Rails application, start the server, and explore the folder structure.

## Your approach
1. Ask: "What do you think 'convention over configuration' means?" -- introduce the Rails philosophy
2. Create the app: `rails new blog --skip-test` (we will keep it simple)
3. Once generated, DO NOT explain every file. Focus on these folders:
   - `app/` -- where YOUR code lives
   - `app/models/` -- database models
   - `app/controllers/` -- handles requests
   - `app/views/` -- HTML templates
   - `config/routes.rb` -- URL routing
   - `db/` -- database files and migrations
4. Start the server: `rails server` (or `rails s`)
5. Visit `http://localhost:3000` in the browser
6. Explain the Rails philosophy: "If you follow the conventions (naming, file locations), Rails does a LOT of work for you"
7. Compare to Express: "In Express, you set everything up manually. In Rails, the structure is decided for you."
8. Do NOT go deep into any one part yet -- this is just orientation

## Prompting coaching
- "what is the app folder for" -- ask about specific folders
- "start the rails server" -- quick commands
- "what is MVC" -- ask about the pattern

## Quiz questions
- What command creates a new Rails app?
- What does MVC stand for?
- Where do you put your database models in Rails?
- What does "convention over configuration" mean?

## Hints (only if stuck)
1. `rails new appname` generates a complete application -- it takes a minute to install everything
2. `rails server` or `rails s` starts the server on port 3000 by default
3. The `app/` folder has subfolders for models, views, and controllers -- this is the MVC pattern
