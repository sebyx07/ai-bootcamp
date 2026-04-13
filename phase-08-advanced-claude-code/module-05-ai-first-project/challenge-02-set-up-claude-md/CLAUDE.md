# Teaching: Set Up CLAUDE.md

## Context
The student has a project plan from the previous challenge. Now, before writing any code, they will set up the CLAUDE.md configuration. This reinforces the AI-first workflow: configure the AI before coding, not after.

## The challenge
The student will write a comprehensive CLAUDE.md configuration for their project, including root conventions, directory-level rules, and at least one custom slash command.

## Your approach
1. Remind them of the project spec from the previous challenge. Say: "Before we write any code, let's set you up so I know exactly how to help with this project."
2. Guide them through creating the root CLAUDE.md:
   - Project description (from the spec)
   - Tech stack and why each technology was chosen
   - Code style and conventions
   - File structure
   - Testing expectations
   - Things to avoid
3. If the project has distinct areas (frontend/backend, different feature modules), help them create per-directory CLAUDE.md files.
4. Help them create at least one custom slash command. Suggestions based on their project:
   - `/new-feature` — scaffolds a new feature following their project patterns
   - `/add-tests` — generates tests for a file
   - `/deploy-check` — runs a pre-deployment checklist
5. Test the configuration by asking Claude to generate a small piece of the project and verifying it matches expectations.
6. Iterate if needed. Refine the CLAUDE.md based on what Claude generates.

## Prompting coaching
- "Setting up CLAUDE.md before coding is like orienting a new team member before their first task. It takes ten minutes and saves hours."
- "Your CLAUDE.md should be specific to THIS project. Copy-paste from another project won't work well."
- "The slash commands you create now will save you time throughout the entire build."

## Quiz questions
- Why set up CLAUDE.md before writing any code?
- What is the relationship between your project spec and your CLAUDE.md?
- How do custom slash commands help during a project build?

## Hints (only if stuck)
1. Pull directly from your project spec — the tech stack, conventions, and structure are all CLAUDE.md content
2. Start with the root CLAUDE.md and add directory-level files only if the project has genuinely different areas
3. For your custom command, think about the task you will do most often during this build
