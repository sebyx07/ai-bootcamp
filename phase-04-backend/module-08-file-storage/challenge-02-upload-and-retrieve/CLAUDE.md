# Teaching: Upload and Retrieve

## Context
The student understands S3 concepts. Now they add file uploads to their blog using Active Storage. For local development, files are stored on disk -- but the pattern is the same as S3.

## The challenge
Add image upload to articles using Rails Active Storage. Display uploaded images on the article page.

## Your approach
1. Set up Active Storage:
   ```
   rails active_storage:install
   rails db:migrate
   ```
2. Add attachment to the Article model:
   ```ruby
   class Article < ApplicationRecord
     has_one_attached :cover_image
   end
   ```
3. Add the file field to the form:
   ```erb
   <%= form.label :cover_image %>
   <%= form.file_field :cover_image %>
   ```
4. Permit the parameter in the controller:
   ```ruby
   def article_params
     params.require(:article).permit(:title, :body, :cover_image)
   end
   ```
5. Display the image in the view:
   ```erb
   <% if @article.cover_image.attached? %>
     <%= image_tag @article.cover_image %>
   <% end %>
   ```
6. Test it: create an article with an image, see it displayed
7. Configure Active Storage to use LocalStack (their local S3):
   - Update `config/storage.yml`:
     ```yaml
     local_s3:
       service: S3
       access_key_id: test
       secret_access_key: test
       region: us-east-1
       bucket: my-bootcamp-bucket
       endpoint: http://localhost:4566
       force_path_style: true
     ```
   - Update `config/environments/development.rb`:
     ```ruby
     config.active_storage.service = :local_s3
     ```
   - Make sure LocalStack is running (from the previous challenge)
8. Test the full flow: upload an image, see it stored in LocalStack, display it
9. Explain: in production you'd just change the endpoint to real AWS S3 — same code, different config

## Prompting coaching
- "add image upload to articles" -- describe the feature
- "show the uploaded image" -- display the file
- "how would I use S3 in production" -- learn about deployment

## Quiz questions
- What does `has_one_attached :cover_image` do?
- Where are uploaded files stored in development?
- How do you check if a file is attached?
- What would you change to use S3 instead of local storage?

## Hints (only if stuck)
1. Run `rails active_storage:install` first -- it creates the necessary database tables
2. `has_one_attached` for one file, `has_many_attached` for multiple files
3. Always check `@article.cover_image.attached?` before trying to display the image
