# Phase 04: Backend — Teaching Guide

## Phase overview

This is the biggest phase in the bootcamp. Students go from zero backend knowledge to building a full Rails blog app. They learn two backend stacks (Node/Express and Ruby/Rails), databases, authentication, and supporting services.

## Student profile at this point

- Comfortable with the terminal and Git
- Can write HTML, CSS, and JavaScript
- Have built frontend projects (possibly React)
- Have NO backend experience -- they do not know what a server is or how HTTP works
- May think "the internet just works" without understanding request/response

## Critical teaching notes

### Module 01 (How the Web Works)
- This is conceptual but must be hands-on -- they need to see real requests and responses
- Use curl and browser dev tools, not just diagrams
- Make sure they understand request/response BEFORE writing server code

### Module 02 (Node/Express)
- Their first backend -- use JavaScript they already know
- Keep it practical: build a working API, not abstract exercises
- This is a stepping stone to Rails, not the main framework

### Module 03 (Ruby Basics)
- Just enough Ruby to read and write Rails code
- Do NOT teach Ruby deeply -- focus on syntax differences from JavaScript
- Use IRB for instant feedback
- Challenge 05 (reading Ruby code) is reverse: show code, ask them to explain it

### Module 04 (Ruby on Rails)
- The big module -- 10 challenges building up to a blog app
- Teach the "Rails way" -- convention over configuration
- Do NOT overwhelm with all Rails magic at once
- Challenge 10 (build-a-blog) is a capstone -- they should do most of the work themselves

### Module 05 (Databases)
- Teach both raw SQL and ORM (ActiveRecord)
- Make sure they understand tables, rows, columns before anything else
- Migrations and seeds are Rails-specific but important

### Module 06 (Auth)
- Security matters -- explain WHY we hash passwords, not just how
- Build actual login/signup, not just theory
- JWT is exposure only -- they will use session-based auth primarily

### Modules 07-09 (Redis, File Storage, Background Jobs)
- These are shorter exposure modules
- Goal: know what the tool is, when you would use it, and basic usage
- Do NOT go deep -- just enough to recognize these in real projects

## Pacing guidance

- Modules 01-02: Days 7-8
- Modules 03-04: Days 8-10
- Module 05: Day 10
- Module 06: Day 11
- Modules 07-09: Day 11 (half day total)

## Common pitfalls

- Students confusing frontend and backend JavaScript
- Not understanding that the browser and server are separate machines
- Copy-pasting Rails generators without understanding the output
- Skipping database fundamentals and struggling with associations
- Getting lost in Rails "magic" without understanding the basics
