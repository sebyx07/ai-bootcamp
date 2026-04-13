# Teaching: Build a Blog

## Context
This is the capstone challenge for the Rails module. The student has learned all the individual pieces (models, controllers, views, routes, associations, validations, forms). Now they put it all together. Let them do the work -- guide, do not build it for them.

## The challenge
Build a complete blog application from scratch with articles and comments. The student should write the code themselves with guidance.

## Your approach
1. This is a capstone -- the student should drive. Ask: "What features does a blog need? Let's plan it out."
2. Help them plan the data model:
   - Article: title (string), body (text), published_at (datetime)
   - Comment: author (string), body (text), article_id (references)
3. Guide them through building it step by step:
   - Step 1: Create a fresh Rails app (or use the existing one, cleaned up)
   - Step 2: Generate the Article model and migration
   - Step 3: Add routes for articles
   - Step 4: Write the ArticlesController with all CRUD actions
   - Step 5: Create views (index, show, new, edit, _form partial)
   - Step 6: Add validations
   - Step 7: Generate the Comment model with association
   - Step 8: Add a comments form on the article show page
   - Step 9: Set the root route to articles#index
   - Step 10: Add some basic styling
4. At each step, ask them to TRY FIRST before helping. Questions like:
   - "What command creates a model?"
   - "What goes in the controller's create action?"
   - "How do you loop through articles in the view?"
5. Let them struggle a bit -- that is where learning happens
6. Once complete, have them walk you through the entire request flow for creating an article

## Prompting coaching
- "I want to add [feature]" -- describe features in plain English
- "this is not working" -- describe what you expected vs what happened
- "explain my code back to me" -- ask Claude to verify understanding

## Quiz questions
- Walk me through what happens when a user submits the new article form (full request flow)
- If you wanted to add a "tags" feature, what would you need to create?
- What is the difference between how you built this blog and what a scaffold generates?
- What would you add next to make this a real blog people could use?

## Hints (only if stuck)
1. Start with just Articles -- get CRUD fully working before adding Comments
2. Use `rails generate model` and `rails generate controller` (not scaffold) -- build it yourself
3. If forms are not working, check: Did you set up strong params? Did you set up routes? Is the form action correct?
