# Teaching: Routes

## Context
The student has seen `resources :articles` in `config/routes.rb` but does not fully understand what it generates. They need to see all 7 RESTful routes and learn to define custom routes.

## The challenge
Explore Rails routing in depth -- understand resourceful routes, custom routes, and the `rails routes` command.

## Your approach
1. Start with `rails routes` -- show the output and explain each column:
   - Prefix (helper method name)
   - Verb (HTTP method)
   - URI Pattern (URL)
   - Controller#Action
2. Explain what `resources :articles` generates:
   - GET /articles -> articles#index
   - GET /articles/new -> articles#new
   - POST /articles -> articles#create
   - GET /articles/:id -> articles#show
   - GET /articles/:id/edit -> articles#edit
   - PATCH /articles/:id -> articles#update
   - DELETE /articles/:id -> articles#destroy
3. Show how to add custom routes:
   ```ruby
   get '/about', to: 'pages#about'
   root 'pages#home'
   ```
4. Explain route helpers: `articles_path`, `article_path(@article)`, `new_article_path`
5. Show `resources` with `only` and `except`:
   ```ruby
   resources :articles, only: [:index, :show]
   ```
6. Have them add a custom route and connect it to a controller action

## Prompting coaching
- "show me all routes" -- use `rails routes`
- "add a route for /about" -- practice custom routes
- "what is articles_path" -- understand route helpers

## Quiz questions
- How many routes does `resources :articles` create?
- What is the difference between `articles_path` and `article_path(1)`?
- How do you set the homepage route in Rails?
- What does `only: [:index, :show]` do?

## Hints (only if stuck)
1. Run `rails routes` to see all defined routes -- use `rails routes | grep article` to filter
2. `root 'controller#action'` sets which page shows at `http://localhost:3000/`
3. Route helpers ending in `_path` generate relative URLs; ending in `_url` generate full URLs
