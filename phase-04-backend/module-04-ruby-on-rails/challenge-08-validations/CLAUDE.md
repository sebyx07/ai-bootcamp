# Teaching: Validations

## Context
The student can create records but there are no rules -- they could create an article with no title. Validations prevent bad data from reaching the database.

## The challenge
Add validations to the Article and Comment models. Test them in the Rails console and see error messages.

## Your approach
1. Ask: "What happens if someone tries to create an article with no title? Try it in the console."
2. Show that it saves successfully -- this is a problem!
3. Add validations to Article:
   ```ruby
   class Article < ApplicationRecord
     has_many :comments, dependent: :destroy
     validates :title, presence: true, length: { minimum: 3, maximum: 100 }
     validates :body, presence: true, length: { minimum: 10 }
   end
   ```
4. Try creating a bad article in the console:
   ```ruby
   article = Article.new(title: "", body: "")
   article.valid?    # false
   article.errors.full_messages  # ["Title can't be blank", ...]
   article.save      # false (does not save!)
   ```
5. Show common validations:
   - `presence: true` -- must not be blank
   - `length: { minimum: 3 }` -- minimum length
   - `uniqueness: true` -- must be unique
   - `numericality: true` -- must be a number
6. Have them add validations to Comment (author and body required)
7. Show how validations affect the form -- errors show up in the view

## Prompting coaching
- "add a validation for..." -- ask for specific rules
- "why did my save fail" -- debug validation errors
- "what validations should I add" -- ask for recommendations

## Quiz questions
- When do validations run? (before saving to the database)
- What does `article.valid?` return?
- How do you see validation error messages?
- What does `presence: true` check for?

## Hints (only if stuck)
1. `validates :field, presence: true` means the field cannot be blank or nil
2. After a failed save, check `article.errors.full_messages` to see what went wrong
3. `.save` returns `false` if validations fail; `.save!` raises an error instead
