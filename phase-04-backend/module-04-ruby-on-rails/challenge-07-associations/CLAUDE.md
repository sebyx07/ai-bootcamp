# Teaching: Associations

## Context
The student has one model (Article). They need to understand how models relate to each other. This is a key concept for building real applications. Use concrete examples.

## The challenge
Create a Comment model that belongs to an Article. Understand has_many/belongs_to and foreign keys.

## Your approach
1. Ask: "If you have Articles and Comments, how are they related?" -- an article HAS MANY comments, a comment BELONGS TO an article
2. Generate the Comment model: `rails generate model Comment author:string body:text article:references`
3. Run `rails db:migrate`
4. Add the association in the Article model:
   ```ruby
   class Article < ApplicationRecord
     has_many :comments, dependent: :destroy
   end
   ```
5. The Comment model already has `belongs_to :article` (from the generator)
6. Test in the Rails console:
   ```ruby
   article = Article.first
   article.comments.create(author: "Alice", body: "Great post!")
   article.comments
   article.comments.count
   ```
7. Explain foreign keys: the comments table has an `article_id` column that links to the articles table
8. Show what `dependent: :destroy` does -- deleting an article also deletes its comments
9. Briefly mention other association types: `has_one`, `has_many :through`

## Prompting coaching
- "add comments to articles" -- describe what you want in plain English
- "how do I get all comments for an article" -- ask about access patterns
- "what is a foreign key" -- ask for explanations

## Quiz questions
- What does `has_many :comments` do?
- What column in the comments table links a comment to its article?
- What does `dependent: :destroy` do?
- What is the difference between `has_many` and `belongs_to`?

## Hints (only if stuck)
1. The model with the foreign key (article_id) is the one that `belongs_to` -- Comment belongs_to Article
2. `article:references` in the generator adds the `article_id` column and the `belongs_to` declaration
3. Use the Rails console to test: `Article.first.comments` should return an array of comments
