# Teaching: Install PostgreSQL

## Context
The student has used Docker and understands services that run in the background. PostgreSQL is a database server -- a program that runs continuously, waiting for connections. They may have never interacted with a database before. Start simple: a database is just an organized way to store data.

## The challenge
Install PostgreSQL, start the service, connect to it, and create a simple database with a table.

## Your approach
1. Explain what a database is: "You know how you save files on your computer? A database is a specialized program for saving structured data -- like a really powerful, queryable spreadsheet."
2. Install PostgreSQL:
   ```
   sudo apt update
   sudo apt install -y postgresql postgresql-contrib
   ```
3. Check it is running: `sudo systemctl status postgresql`
4. Explain that PostgreSQL creates a system user called `postgres`. Connect as that user:
   ```
   sudo -u postgres psql
   ```
5. Walk through basic SQL commands inside psql:
   ```sql
   CREATE DATABASE bootcamp;
   \c bootcamp
   CREATE TABLE students (id SERIAL PRIMARY KEY, name TEXT, progress TEXT);
   INSERT INTO students (name, progress) VALUES ('Your Name', 'Phase 02');
   SELECT * FROM students;
   ```
6. Explain each command:
   - `CREATE DATABASE` — makes a new database
   - `\c` — connects to a database
   - `CREATE TABLE` — defines a structure for your data
   - `INSERT INTO` — adds a row
   - `SELECT * FROM` — reads all rows
7. Show them `\dt` (list tables), `\l` (list databases), `\q` (quit).
8. Create a password for the postgres user:
   ```sql
   ALTER USER postgres PASSWORD 'password';
   ```
9. Show them how to connect with a password: `psql -U postgres -h localhost`

## Prompting coaching
- Teach: "How do I connect to my database?"
- Encourage: "Explain SQL like I have never seen it before."
- Model: "What is the difference between a database and a table?"

## Quiz questions
- What port does PostgreSQL run on by default?
- What is the difference between a database and a table?
- What does `sudo -u postgres psql` do and why do you need `sudo -u postgres`?
- What does SERIAL PRIMARY KEY mean?

## Hints (only if stuck)
1. If PostgreSQL is not running: `sudo systemctl start postgresql`.
2. If they cannot connect, make sure they are using `sudo -u postgres psql`.
3. SQL commands end with a semicolon. If the prompt changes to `bootcamp-#`, they forgot the semicolon.
