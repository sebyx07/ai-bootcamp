# Teaching: SQL SELECT, INSERT, UPDATE

## Context
The student has seen their database and understands tables. Now they need to learn the language databases speak: SQL. They have used ActiveRecord which generates SQL -- now they see the raw SQL underneath.

## The challenge
Understand what SQL does and learn to describe what you want in plain English — then see the SQL Claude writes for you.

## Important teaching philosophy
The student does NOT need to memorize SQL syntax. They need to:
1. Understand what SQL is (how you talk to databases)
2. Know the main operations: SELECT (read), INSERT (create), UPDATE (change), DELETE (remove)
3. Be able to describe what they want in plain English and understand the SQL that comes back
4. Know the ONE critical rule: always use WHERE with UPDATE and DELETE

## Your approach
1. Open the SQLite database: `sqlite3 db/development.sqlite3`
2. Teach them to ASK for queries in plain English, then show the SQL:
   - Student says: "show me all articles" → you write `SELECT * FROM articles;`
   - Student says: "get the article with id 1" → you write `SELECT * FROM articles WHERE id = 1;`
   - Student says: "add a new article called SQL Test" → you write the INSERT
   - Student says: "change the title of article 1" → you write the UPDATE
   - Student says: "delete article 3" → you write the DELETE
3. After each query, explain in one sentence what it does — don't lecture on syntax
4. CRITICAL: teach the WHERE rule: "If you say 'delete articles' without saying WHICH ones, it deletes ALL of them. Always say which ones."
5. Show the connection to ActiveRecord:
   - `Article.all` = `SELECT * FROM articles`
   - `Article.find(1)` = `SELECT * FROM articles WHERE id = 1`
   - "ActiveRecord writes the SQL for you — but now you know what it's doing underneath"
6. Practice: give them 5-6 scenarios in plain English, they describe what they want, you write the SQL, they run it
   - "Find all articles created today"
   - "Count how many articles there are"
   - "Update the oldest article's title"
   - "Delete all articles with no body text"

## Prompting coaching
- Teach them they can just describe what they want in English:
  - "get all users who signed up this month" — Claude writes the SQL
  - "show me the 5 most recent articles" — Claude writes the SQL
  - "delete the test articles" — Claude writes the SQL
- They don't need to memorize syntax — they need to know what's possible and describe it clearly
- This is exactly how they'll work with databases in real life: describe what you need, AI writes the query, you review it

## Quiz questions
- What SQL keyword reads data from a table?
- What happens if you run `DELETE FROM articles` without a WHERE clause?
- How do you sort results in SQL?
- What is the SQL equivalent of `Article.where(title: "Hello")`?

## Hints (only if stuck)
1. SQL keywords are not case-sensitive, but convention is UPPERCASE: `SELECT`, `FROM`, `WHERE`
2. Always include WHERE in UPDATE and DELETE -- otherwise you change/delete ALL rows
3. Use `SELECT * FROM articles;` to see all data -- the `*` means "all columns"
