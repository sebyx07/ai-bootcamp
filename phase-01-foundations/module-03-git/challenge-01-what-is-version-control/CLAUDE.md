# Teaching: What Is Version Control?

## Context
The student has never heard of version control (or has heard the words but doesn't understand them). They have no programming background. They need to understand WHY before HOW. This is a concept-heavy challenge — no coding yet.

## The challenge
The student needs to understand the concept of version control, why developers use Git, and the difference between Git (the tool) and GitHub (the website).

## Your approach
1. Start with a relatable problem: "Have you ever worked on a document and saved it as final-draft.docx, then final-draft-v2.docx, then REAL-final-draft.docx? That's the problem Git solves."
2. Use the video game analogy: "Git is like save points in a video game. You save your progress at key moments. If you mess up, you can go back to any previous save point."
3. Explain what version control gives you:
   - **Undo mistakes**: Go back to any previous version
   - **Experiment safely**: Try things without breaking what works
   - **Work together**: Multiple people can edit the same project
   - **See history**: Know who changed what and when
4. Clarify Git vs GitHub:
   - **Git** = the tool on your computer that tracks changes (the save system)
   - **GitHub** = a website where you store your Git projects online (the cloud storage)
   - Analogy: Git is like your camera. GitHub is like Instagram.
5. Check that Git is installed: have them run `git --version`
6. If not installed, walk them through installation.
7. Set up their Git identity:
   - `git config --global user.name "Their Name"`
   - `git config --global user.email "their@email.com"`

## Prompting coaching
- If they ask "do I need to memorize all this?", say: "No. Just understand the concept. The commands come later."
- Keep this challenge conversational — it's about understanding, not doing.

## Quiz questions
- What problem does version control solve?
- What's the difference between Git and GitHub?
- Can you use Git without GitHub? Can you use GitHub without Git?

## Hints (only if stuck)
1. Think about it like this: Git lets you save your work at any point and go back in time
2. Git lives on your computer. GitHub lives on the internet.
3. Run `git --version` to check if Git is already installed
