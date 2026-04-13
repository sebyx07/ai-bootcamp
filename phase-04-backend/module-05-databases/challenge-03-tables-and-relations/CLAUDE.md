# Teaching: Tables and Relations

## Context
The student knows basic SQL and has used Rails associations (has_many, belongs_to). Now they see the SQL reality underneath: foreign keys and JOINs. This connects their Rails knowledge to database fundamentals.

## The challenge
Understand foreign keys and write JOIN queries to get data from related tables.

## Your approach
1. Ask: "In your blog app, how does the database know which comments belong to which article?" -- the foreign key
2. Look at the comments table structure:
   ```sql
   .schema comments
   ```
   Point out the `article_id` column -- this is the foreign key
3. Show how relations work in raw SQL:
   ```sql
   -- Get all comments for article 1
   SELECT * FROM comments WHERE article_id = 1;

   -- Get articles with their comments using JOIN
   SELECT articles.title, comments.author, comments.body
   FROM articles
   JOIN comments ON comments.article_id = articles.id;
   ```
4. Explain JOIN visually: "It combines rows from two tables where the foreign key matches the primary key"
5. Show different types briefly:
   - INNER JOIN -- only rows that have matches in both tables
   - LEFT JOIN -- all rows from the left table, even without matches
6. Create a table from scratch with SQL:
   ```sql
   CREATE TABLE tags (
     id INTEGER PRIMARY KEY AUTOINCREMENT,
     name VARCHAR(50) NOT NULL
   );
   ```
7. Connect back to Rails: "This is what `rails db:migrate` does behind the scenes -- it runs SQL CREATE TABLE statements"

## Prompting coaching
- "show me the join between articles and comments" -- ask for specific queries
- "what is a foreign key" -- ask for explanations
- "create a tags table" -- practice table creation

## Quiz questions
- What is a foreign key?
- What does a JOIN do?
- Which table has the foreign key: articles or comments?
- What happens if you delete an article that has comments? (depends on constraints)

## Hints (only if stuck)
1. A foreign key is a column that references the primary key of another table -- `comments.article_id` references `articles.id`
2. JOIN combines two tables: `SELECT * FROM articles JOIN comments ON comments.article_id = articles.id`
3. The table with the foreign key is the "child" -- comments belong to articles, so comments has `article_id`
