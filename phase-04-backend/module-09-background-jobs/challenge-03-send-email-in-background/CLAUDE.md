# Teaching: Send Email in Background

## Context
The student has Sidekiq working with a simple job. Now they do something real: send an email when a new comment is posted. This ties together Action Mailer and background jobs.

## The challenge
Create a mailer that sends a notification email when someone comments on an article. Send it using a background job so the user does not wait.

## Your approach
1. Generate a mailer:
   ```
   rails generate mailer CommentNotification
   ```
2. Write the mailer (`app/mailers/comment_notification_mailer.rb`):
   ```ruby
   class CommentNotificationMailer < ApplicationMailer
     def new_comment(article, comment)
       @article = article
       @comment = comment
       mail(to: "author@example.com", subject: "New comment on #{@article.title}")
     end
   end
   ```
3. Create the email view (`app/views/comment_notification_mailer/new_comment.html.erb`):
   ```erb
   <h1>New Comment on "<%= @article.title %>"</h1>
   <p><strong><%= @comment.author %></strong> said:</p>
   <p><%= @comment.body %></p>
   ```
4. Send the email in the background when a comment is created:
   ```ruby
   # In CommentsController#create
   CommentNotificationMailer.new_comment(@article, @comment).deliver_later
   ```
5. Explain: `deliver_later` uses Active Job (which uses Sidekiq) to send the email in the background
6. For development, set up Letter Opener or check the Rails log for the email content:
   ```ruby
   # config/environments/development.rb
   config.action_mailer.delivery_method = :letter_opener
   # OR just check the Rails server log -- it shows the email content
   ```
7. Test it: create a comment and watch the Sidekiq terminal process the email job
8. Explain: in production, you would configure a real email service (SendGrid, Postmark, etc.)

## Prompting coaching
- "send an email when a comment is created" -- describe the feature
- "my email is not sending" -- troubleshoot mailer setup
- "how do I see the email in development" -- preview emails locally

## Quiz questions
- What is the difference between `deliver_now` and `deliver_later`?
- Where do email templates live in a Rails app?
- Why should emails be sent in the background?
- What would you change to send real emails in production?

## Hints (only if stuck)
1. `deliver_later` sends via Sidekiq (background); `deliver_now` sends immediately (blocks the request)
2. Email views live in `app/views/mailer_name/` -- just like regular views but for emails
3. In development, check the Rails server log -- it prints the full email content there
