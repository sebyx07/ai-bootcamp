# Teaching: Deploy a Rails App

## Context
The student just walked through deploying a Node app. Rails deployment is similar in concept but has its own tools and steps. The key differences: Puma instead of PM2, bundle install instead of npm install, database migrations, asset precompilation. Use the Node deployment as a reference point.

## The challenge
Walk through (or execute) the full deployment of a Rails app: get it on a server, install Ruby, install dependencies, set up the database, run Puma, and configure Nginx.

## Your approach
1. Compare to the Node deployment: "Same concept, different tools."
2. Review the Rails-specific deployment steps:
   - Install Ruby (via rbenv) on the server
   - Clone the repo and `bundle install`
   - Set up environment variables (especially `RAILS_ENV=production`, `SECRET_KEY_BASE`, `DATABASE_URL`)
   - Create and migrate the production database: `rails db:create db:migrate RAILS_ENV=production`
   - Precompile assets: `rails assets:precompile RAILS_ENV=production`
   - Start Puma (Rails' default app server)
   - Configure Nginx to reverse proxy to Puma
3. Explain Puma: "Puma is Rails' built-in app server. It handles multiple requests at once using threads. It is the equivalent of PM2 for Node."
4. If simulating locally:
   - Run the app in production mode: `RAILS_ENV=production rails server`
   - Point Nginx at it (reverse proxy from Module 01)
5. Discuss Rails-specific gotchas:
   - Forgetting to run migrations on the server
   - Missing `SECRET_KEY_BASE` environment variable
   - Assets not precompiled (CSS/JS missing in production)
6. Briefly mention modern tools like Kamal (Rails 8's deployment tool) and platforms like Render/Railway that simplify this.

## Prompting coaching
"What is different about deploying rails vs node?" is a good comparative question. "Why are my assets missing in production?" is a common debugging prompt they should know.

## Quiz questions
- What does `rails assets:precompile` do and why is it necessary in production?
- What is the `SECRET_KEY_BASE` and why does Rails need it?
- Name two things you must do on the server after cloning a Rails app that you would not do for a Node app.

## Hints (only if stuck)
1. The biggest Rails-specific steps are: `bundle install`, `rails db:migrate`, and `rails assets:precompile`.
2. Generate a secret key with `rails secret` and set it as `SECRET_KEY_BASE` in your environment.
3. If the app loads but looks unstyled, you probably forgot to precompile assets.
