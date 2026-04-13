# Teaching: Forms and Strong Params

## Context
The student can create records in the console but users need forms in the browser. They need to understand Rails form helpers and the security concept of strong parameters.

## The challenge
Build forms for creating and editing articles, and implement strong parameters to whitelist allowed fields.

## Your approach
1. Ask: "How do users currently create articles in your app?" -- through the scaffold form. Now let's understand how it works.
2. Look at the scaffold form together:
   ```erb
   <%= form_with(model: @article) do |form| %>
     <%= form.label :title %>
     <%= form.text_field :title %>
     <%= form.label :body %>
     <%= form.text_area :body %>
     <%= form.submit %>
   <% end %>
   ```
3. Explain what `form_with` does: generates HTML `<form>` with the right action and method
4. Explain strong parameters -- WHY they exist:
   - Without them, a user could submit ANY field (like `admin: true`)
   - Strong params whitelist which fields are allowed
5. Show the private method in the controller:
   ```ruby
   private
   def article_params
     params.require(:article).permit(:title, :body)
   end
   ```
6. Show how to display validation errors in the form:
   ```erb
   <% if @article.errors.any? %>
     <ul>
       <% @article.errors.full_messages.each do |error| %>
         <li><%= error %></li>
       <% end %>
     </ul>
   <% end %>
   ```
7. Have them build a comment form on the article show page

## Prompting coaching
- "build a form for comments" -- practice form helpers
- "what are strong params" -- ask for explanations
- "show validation errors in the form" -- improve user experience

## Quiz questions
- Why do strong parameters exist? (security -- prevent mass assignment)
- What does `params.require(:article).permit(:title, :body)` do?
- What Rails helper generates a form?
- How does `form_with(model: @article)` know whether to create or update?

## Hints (only if stuck)
1. `form_with(model: @article)` automatically sets the form action -- if `@article` is new, it POSTs; if it exists, it PATCHes
2. Strong params MUST be in a private method -- the controller uses it in `create` and `update` actions
3. `params.permit(:title, :body)` only allows title and body -- anything else is silently dropped
