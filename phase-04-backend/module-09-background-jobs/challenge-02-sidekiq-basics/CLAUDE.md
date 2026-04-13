# Teaching: Sidekiq Basics

## Context
The student understands why background jobs exist. Now they set up Sidekiq and create their first job. Redis must be running for Sidekiq to work.

## The challenge
Install Sidekiq, create a simple background job, and see it processed.

## Your approach
1. Make sure Redis is running: `redis-cli ping` (should return PONG)
2. Add Sidekiq to Gemfile:
   ```ruby
   gem 'sidekiq'
   ```
   Run `bundle install`
3. Configure Active Job to use Sidekiq in `config/application.rb`:
   ```ruby
   config.active_job.queue_adapter = :sidekiq
   ```
4. Create a job:
   ```
   rails generate job HelloWorld
   ```
5. Edit the job (`app/jobs/hello_world_job.rb`):
   ```ruby
   class HelloWorldJob < ApplicationJob
     queue_as :default

     def perform(name)
       puts "Hello, #{name}! This ran in the background at #{Time.now}"
     end
   end
   ```
6. Start Sidekiq in a separate terminal: `bundle exec sidekiq`
7. Enqueue the job from the Rails console:
   ```ruby
   HelloWorldJob.perform_later("Alice")
   ```
8. Watch the Sidekiq terminal -- it should show the job being processed
9. Show `perform_later` (async) vs `perform_now` (sync -- runs immediately, no queue)
10. Optionally show the Sidekiq web UI by mounting it in routes

## Prompting coaching
- "create a background job" -- ask for specific jobs
- "start sidekiq" -- get the worker running
- "my job is not running" -- troubleshoot the queue

## Quiz questions
- What command starts the Sidekiq worker process?
- What is the difference between `perform_later` and `perform_now`?
- Why does Sidekiq need Redis?
- Where do job classes live in a Rails app?

## Hints (only if stuck)
1. You need THREE things running: Rails server, Redis, and Sidekiq -- each in its own terminal
2. `perform_later` adds the job to the Redis queue; `perform_now` runs it immediately (skips the queue)
3. Check the Sidekiq terminal output -- it shows when jobs are picked up and completed
