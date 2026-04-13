# Teaching: Views and ERB

## Context
The student knows HTML from the frontend phase. ERB is just HTML with Ruby mixed in. They need to understand the two ERB tags and how to display data from the controller.

## The challenge
Write ERB views that display data from the controller, loop through collections, and use layouts and partials.

## Your approach
1. Ask: "You know HTML. ERB is HTML with Ruby sprinkled in. Ready to see how?"
2. Explain the two ERB tags:
   - `<%= expression %>` -- evaluates AND outputs (the `=` means "print this")
   - `<% code %>` -- evaluates but does NOT output (for logic like loops and conditions)
3. Start with a simple view:
   ```erb
   <h1>Articles</h1>
   <% @articles.each do |article| %>
     <h2><%= article.title %></h2>
     <p><%= article.body %></p>
   <% end %>
   ```
4. Explain layouts: `app/views/layouts/application.html.erb` wraps every page
   - `<%= yield %>` is where the page content goes
5. Introduce partials:
   - Create `_article.html.erb` (note the underscore)
   - Render it: `<%= render @articles %>`
6. Show link helpers: `<%= link_to "Show", article_path(article) %>`
7. Have them customize the article views -- change the layout, add styling, create a partial

## Prompting coaching
- "what is the difference between <%= and <%" -- essential ERB question
- "add a link to each article" -- practice helpers
- "create a partial for..." -- practice partials

## Quiz questions
- What does `<%= %>` do that `<% %>` does not?
- Where is the main layout file in Rails?
- What does `<%= yield %>` do in a layout?
- How do you name a partial file? (starts with underscore)

## Hints (only if stuck)
1. `<%= %>` with the equals sign OUTPUTS to the page; `<% %>` without it just runs the code
2. Partials start with an underscore: `_article.html.erb`, but you render them without the underscore: `render 'article'`
3. `link_to "text", path` generates an `<a>` tag -- it is Rails' way of creating links
