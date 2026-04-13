# Teaching: Models

## Context
The student has seen the scaffold and knows models exist. Now they need to understand models deeply -- they are the foundation of Rails. Use the Rails console for hands-on exploration.

## The challenge
Use the Rails console to interact with models directly. Understand CRUD operations through ActiveRecord.

## Your approach
1. Open the Rails console: `rails console` (or `rails c`)
2. Start with basic operations on the Article model:
   - Create: `Article.create(title: "My First Post", body: "Hello world")`
   - Read all: `Article.all`
   - Read one: `Article.find(1)`
   - Update: `article = Article.find(1); article.update(title: "Updated Title")`
   - Delete: `article = Article.find(1); article.destroy`
3. Explain ActiveRecord: "Your model is a Ruby class that talks to the database. Each instance is a row."
4. Show query methods:
   - `Article.where(title: "My First Post")`
   - `Article.first`, `Article.last`
   - `Article.count`
   - `Article.order(created_at: :desc)`
5. Explain: "You never write SQL directly -- ActiveRecord translates Ruby methods into SQL"
6. Show them the SQL that ActiveRecord generates (it prints in the console)
7. Create a new model from scratch (not scaffold): `rails generate model Comment author:string body:text article_id:integer`

## Prompting coaching
- "create an article in the console" -- practice CRUD
- "find all articles with..." -- practice queries
- "what SQL does this generate" -- understand ActiveRecord

## Quiz questions
- What is ActiveRecord?
- What is the difference between `.new` and `.create`?
- How do you find all articles with a specific title?
- What happens to the database when you call `.destroy` on a record?

## Hints (only if stuck)
1. `rails console` gives you a Ruby environment with all your models loaded -- try `Article.all`
2. `.create` saves to the database immediately; `.new` creates an object in memory that you must `.save` manually
3. Watch the console output -- it shows the SQL queries that ActiveRecord generates
