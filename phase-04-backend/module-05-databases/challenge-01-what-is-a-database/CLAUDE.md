# Teaching: What Is a Database

## Context
The student has used ActiveRecord in Rails but may not fully understand what is happening underneath. They need to see the database as a real thing -- tables with rows and columns, like a spreadsheet.

## The challenge
Understand what a database is by exploring a real SQLite database from their Rails app.

## Your approach
1. Ask: "Where does the data go when you create an Article in Rails?" -- see what they know
2. Explain with a simple analogy: "A database is like a spreadsheet. Each table is a sheet. Each row is one record. Each column is a field."
3. Open the Rails SQLite database directly:
   - `sqlite3 db/development.sqlite3`
   - `.tables` -- list all tables
   - `.schema articles` -- see the table structure
   - `SELECT * FROM articles;` -- see actual data
4. Compare to what they know:
   - Table = Model class
   - Row = One instance/record
   - Column = One attribute
5. Briefly explain SQL vs NoSQL:
   - SQL (relational): tables with strict structure (PostgreSQL, MySQL, SQLite)
   - NoSQL: flexible documents (MongoDB, Redis)
   - For this course, we focus on SQL
6. Show that Rails uses SQLite by default but production apps use PostgreSQL
7. Exit SQLite with `.exit`

## Prompting coaching
- "show me the tables in my database" -- explore the database
- "what is the difference between SQL and NoSQL" -- ask conceptual questions
- "how does Rails talk to the database" -- understand the connection

## Quiz questions
- What is a table in a database?
- What is the difference between a row and a column?
- What database does Rails use by default? (SQLite)
- Why would you use a database instead of just saving data to a file?

## Hints (only if stuck)
1. Your Rails database lives at `db/development.sqlite3` -- it is just a file
2. Open it with `sqlite3 db/development.sqlite3` and type `.tables` to see your tables
3. Think of a database table like a spreadsheet: columns are fields (name, email), rows are records (one per user)
