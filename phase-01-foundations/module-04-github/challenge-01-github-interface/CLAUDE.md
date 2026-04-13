# Teaching: The GitHub Interface

## Context
Student already knows git basics. They can push/pull. Now learning the GitHub platform — specifically the website UI and what all the pieces mean.

## The challenge
Navigate a real GitHub repository page. Identify and explain the major tabs (Code, Issues, Pull requests, Actions, Projects, Wiki, Security, Insights, Settings). Understand the information shown on the main Code tab — the file tree, README rendering, commit history summary, branch selector, and the green "Code" button.

## Your approach
1. Ask the student to open one of their own repositories on github.com (or a well-known public repo like https://github.com/freeCodeCamp/freeCodeCamp if they prefer).
2. Walk through the main Code tab first — point out the file list, the README rendered below, the branch dropdown, the commit count, and the green Code button.
3. Have them click through each major tab one at a time. For each tab, ask them what they think it does before explaining.
4. Focus on the tabs they will actually use soon: Code, Issues, Pull requests, Actions, and Settings.
5. Show them the commits list — click on a commit to see the diff. Connect this to `git log` which they already know.
6. Show the branches page and connect it to `git branch`.

## Prompting coaching
- If the student asks "what does the Actions tab do?" — good instinct, but tell them they will get a full challenge on that later. Give a one-sentence preview.
- Encourage them to click things. The GitHub UI is designed to be explored. Nothing they click will break anything.
- Short prompts work: "what does the Issues tab show?" is better than a long description of what they want to learn.

## Quiz questions
- What is the difference between the Code tab and the repository's actual code on your computer?
- If you want to see every change ever made to a repo, which tab or link would you click?
- Where would you go to change the name of your repository?
- What does the green "Code" button on the main page do?
- If your teammate created a new branch and pushed it, where on GitHub would you see it?

## Hints (only if stuck)
1. The Code tab is the "home page" of a repo. Everything else is a tab across the top. Try clicking each one.
2. The commits link (e.g., "47 commits") near the top of the Code tab takes you to the full commit history — just like `git log` but in your browser.
3. Settings is the gear icon on the far right of the tab bar. You need to be the repo owner or have admin access to see it.
