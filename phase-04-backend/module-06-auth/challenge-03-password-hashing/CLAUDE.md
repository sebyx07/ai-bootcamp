# Teaching: Password Hashing

## Context
The student is about to build login/signup. Before they do, they MUST understand why passwords are hashed. This is a security fundamental that every developer needs.

## The challenge
Understand password hashing, try it in the console, and set up `has_secure_password` in Rails.

## Your approach
1. Ask: "If a hacker steals your database, and passwords are stored as plain text, what happens?" -- everyone's password is exposed
2. Explain hashing:
   - Hashing is a ONE-WAY function: password -> hash (you cannot go backwards)
   - Same input always gives the same hash
   - Different from encryption (which CAN be reversed)
3. Show it in Ruby/Rails:
   ```ruby
   require 'bcrypt'
   hash = BCrypt::Password.create("my_password")
   # => "$2a$12$LJ3m4y..."
   BCrypt::Password.new(hash) == "my_password"  # true
   BCrypt::Password.new(hash) == "wrong"         # false
   ```
4. Explain salting: bcrypt adds random data (a "salt") so the same password produces different hashes
5. Set up `has_secure_password` in Rails:
   - Add `bcrypt` to Gemfile: `gem 'bcrypt'`
   - Run `bundle install`
   - Add `password_digest` column to User model
   - Add `has_secure_password` to the model
6. Show how it works:
   ```ruby
   user = User.create(name: "Alice", email: "alice@example.com", password: "secret123")
   user.authenticate("secret123")  # returns the user
   user.authenticate("wrong")       # returns false
   ```
7. Key rule: "You NEVER store the password. You store the hash. When someone logs in, you hash what they typed and compare."

## Prompting coaching
- "why not just store the password" -- explore the security problem
- "what is bcrypt" -- ask about the tool
- "hash this password" -- try it in the console

## Quiz questions
- What is the difference between hashing and encryption?
- Can you convert a hash back to the original password?
- What is a salt in password hashing?
- What column name does Rails expect for hashed passwords? (password_digest)

## Hints (only if stuck)
1. Hashing is ONE-WAY: you can go from password to hash, but NEVER from hash back to password
2. `has_secure_password` in Rails gives you `.authenticate()` and automatically hashes passwords
3. The column must be named `password_digest` -- Rails convention
