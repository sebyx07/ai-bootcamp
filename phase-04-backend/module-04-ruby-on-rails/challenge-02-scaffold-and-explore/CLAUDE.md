# Teaching: Scaffold and Explore

## Context
The student has a Rails app but has not added any features. The scaffold generator is the fastest way to see all the pieces of Rails working together. Use it as a teaching tool, then explain each piece.

## The challenge
Run a scaffold generator, explore everything it creates, and understand how all the pieces connect.

## Your approach
1. Run the scaffold: `rails generate scaffold Article title:string body:text`
2. Run the migration: `rails db:migrate`
3. Start the server and visit `http://localhost:3000/articles`
4. Walk through the CRUD operations in the browser: create, read, update, delete
5. NOW explore the generated files one by one:
   - `app/models/article.rb` -- the model (very simple right now)
   - `app/controllers/articles_controller.rb` -- the controller (all 7 actions)
   - `app/views/articles/` -- the view templates
   - `config/routes.rb` -- `resources :articles`
   - `db/migrate/...create_articles.rb` -- the migration
6. Explain how a request flows: URL -> route -> controller -> model -> view -> response
7. Emphasize: "Scaffolds are great for learning, but in real projects you build each piece yourself -- which is what we will do next"

## Prompting coaching
- "what did the scaffold create" -- ask for a file list
- "show me the controller" -- explore specific files
- "how does the request flow" -- understand the full cycle

## Quiz questions
- What command generates a scaffold in Rails?
- What does `rails db:migrate` do?
- How many controller actions does a scaffold create? (7: index, show, new, create, edit, update, destroy)
- What file defines which URLs map to which controller actions?

## Hints (only if stuck)
1. After generating the scaffold, you MUST run `rails db:migrate` before the app will work
2. Look at `config/routes.rb` -- `resources :articles` creates all 7 RESTful routes automatically
3. The controller actions follow a pattern: index (list), show (one), new (form), create (save), edit (form), update (save), destroy (delete)
