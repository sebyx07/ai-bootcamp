# Teaching: Controllers

## Context
The student has used models in the Rails console. They have seen the scaffold-generated controller. Now they need to understand controllers as the "traffic cop" between routes, models, and views.

## The challenge
Write controller actions from scratch, understanding what each action does and how it connects to the route and view.

## Your approach
1. Ask: "In Express, what handles a request? (route handler). In Rails, what does that job?" (controller action)
2. Open the scaffold-generated `articles_controller.rb` and walk through it:
   - `index` -- gets all articles, makes them available to the view
   - `show` -- gets one article by ID
   - `new` -- creates an empty article for the form
   - `create` -- saves a new article from form data
   - `edit` -- finds the article to edit
   - `update` -- updates the article from form data
   - `destroy` -- deletes the article
3. Explain instance variables (`@articles`, `@article`) -- they pass data to views
4. Show the flow: route calls controller action -> action sets instance variable -> view uses it
5. Have them create a new controller from scratch:
   - `rails generate controller Pages home about contact`
   - Write simple actions that set instance variables
6. Compare to Express:
   - Express: `res.json(data)` or `res.render('template', data)`
   - Rails: set `@variable`, Rails automatically renders the matching view
7. Explain `redirect_to` vs rendering a view

## Prompting coaching
- "what does the index action do" -- ask about specific actions
- "write a controller for..." -- create from scratch
- "how does the view get data from the controller" -- understand the connection

## Quiz questions
- What is the job of a controller in MVC?
- How does a view access data from a controller? (instance variables)
- What is the difference between `render` and `redirect_to`?
- How many standard RESTful actions does a Rails controller have?

## Hints (only if stuck)
1. Instance variables (starting with `@`) in the controller are automatically available in the view
2. Rails automatically renders a view matching the action name -- `index` action renders `index.html.erb`
3. Use `redirect_to` after create/update/destroy to send the user to a different page
