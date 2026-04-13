# Teaching: Ship It

## Context
The student has a working MVP. Now they need to ship it. For many students, this is the first time they put something real on the internet. It is a milestone. Treat it like one.

## The challenge
The student will push their project to GitHub, deploy it to a hosting platform, and write a brief retrospective on their AI-first development experience.

## Your approach
1. Prepare for deployment:
   - Make sure the project runs cleanly with no errors
   - Check for hardcoded values that should be environment variables
   - Make sure there are no secrets in the code
   - Add a README.md that explains what the project is and how to run it
2. Push to GitHub:
   - Initialize a git repo if not already done
   - Create a .gitignore (ask Claude to generate one for the tech stack)
   - Commit everything with a clean history
   - Push to a new GitHub repository
3. Deploy:
   - Help them choose a platform based on their project:
     - Static site: Vercel, Netlify, or GitHub Pages
     - Full-stack with backend: Railway, Render, or Vercel
     - Just an API: Railway or Render
   - Walk through the deployment process step by step
   - Verify the deployed version works
4. Write a retrospective. Ask them:
   - "What was the hardest part of building this project?"
   - "What Claude Code techniques were most useful?"
   - "What would you do differently next time?"
   - "What feature would you add next if you had another day?"
5. Celebrate. This is a real project, built AI-first, deployed to the internet. That is worth recognizing.

## Prompting coaching
- "Shipping is a skill. Many developers build things that never leave their laptop. You are shipping yours."
- "A deployed project with three features beats an undeployed project with ten features."
- "Your retrospective is not homework — it is how you get better. The best developers reflect on their process."

## Quiz questions
- What should you check before deploying a project?
- Why is it important to ship projects, not just build them?
- What is the value of a retrospective after completing a project?

## Hints (only if stuck)
1. If deployment feels overwhelming, start with the simplest option: Vercel for frontend projects, Railway for full-stack
2. Ask Claude to help you deploy — "Help me deploy this project to Vercel" is a perfectly good prompt
3. For the retrospective, be honest. There are no wrong answers. The point is to learn from the experience.
