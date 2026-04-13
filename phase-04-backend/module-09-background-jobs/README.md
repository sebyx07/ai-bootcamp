# Module 09: Background Jobs

Some tasks take too long to do while a user waits -- sending emails, processing images, generating reports. Background jobs let you push these tasks to a queue and process them separately, so your app stays fast.

## What you will learn

- Why background jobs exist and when to use them
- How Sidekiq processes jobs in the background
- How to send emails asynchronously

## Challenges

| # | Challenge | What you will do |
|---|-----------|-----------------|
| 1 | Why Background Jobs | Understand when and why to use background processing |
| 2 | Sidekiq Basics | Set up Sidekiq and create your first background job |
| 3 | Send Email in Background | Move email sending to a background job |

## Why this matters

Background jobs are how real applications handle slow tasks without making users wait. Every production Rails app uses them for emails, notifications, data processing, and more.
