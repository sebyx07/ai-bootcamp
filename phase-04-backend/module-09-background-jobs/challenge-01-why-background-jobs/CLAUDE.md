# Teaching: Why Background Jobs

## Context
The student has built a working blog. Now they need to understand why certain tasks (like sending emails) should NOT happen during the web request. This is a concept-first challenge.

## The challenge
Understand why background jobs exist, what problems they solve, and how job queues work.

## Your approach
1. Ask: "When a user signs up, you want to send them a welcome email. Should you send it while they wait for the page to load?"
2. Explain the problem:
   - A web request should be fast (under 500ms ideally)
   - Sending an email takes 2-5 seconds (connecting to email server, etc.)
   - The user stares at a loading spinner for 5 seconds -- bad experience
   - If the email server is down, the signup FAILS -- even worse
3. The solution: background jobs
   - Instead of doing the slow task during the request, you put it in a QUEUE
   - A separate worker process picks up jobs from the queue and does them
   - The web request finishes immediately, the email is sent moments later
4. Real-world examples of background jobs:
   - Sending emails (welcome, notifications, password reset)
   - Processing uploaded images (resizing, thumbnails)
   - Generating reports or PDFs
   - Syncing data with external services
   - Sending push notifications
5. Explain the queue concept:
   - Jobs are added to a queue (stored in Redis)
   - Worker processes run separately and pick up jobs
   - If a job fails, it can be retried
6. Introduce Sidekiq: the most popular background job framework for Ruby/Rails, powered by Redis

## Prompting coaching
- "why use background jobs" -- ask for the reasoning
- "what tasks should be background jobs" -- explore use cases
- "how does a job queue work" -- understand the pattern

## Quiz questions
- Why should you not send an email during a web request?
- What data store does Sidekiq use to manage its job queue?
- What happens if a background job fails?
- Name 3 tasks that should be background jobs.

## Hints (only if stuck)
1. Think of a restaurant: the waiter (web request) takes your order quickly and goes to the next table; the kitchen (background worker) prepares the food separately
2. Job queues are like a to-do list: jobs get added, workers check the list and do each one
3. Sidekiq uses Redis to store the queue -- that is why Redis is needed
