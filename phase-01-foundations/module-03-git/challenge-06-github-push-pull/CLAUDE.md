# Teaching: GitHub — Push and Pull

## Context
The student has been working locally. Now they connect to GitHub — putting their code on the internet. This is exciting (their first public repo!) but also involves new concepts: remotes, push, pull, and authentication.

## The challenge
The student needs to create a GitHub repository, connect their local project to it, and push their code up.

## Your approach
1. First, check they have a GitHub account. If not, help them create one at github.com.
2. Check authentication. They'll need either:
   - GitHub CLI (`gh auth login`) — recommended, simplest approach
   - SSH key set up
   - Personal access token
   - Walk them through whichever is appropriate for their setup.
3. Create a repo on GitHub:
   - Option A: Use `gh repo create my-project --public --source=.` if they have the GitHub CLI
   - Option B: Walk them through the GitHub web interface
4. Connect local to remote:
   - `git remote add origin https://github.com/username/repo-name.git`
   - Explain: "`origin` is just a nickname for the GitHub URL. It's like saving a contact in your phone instead of typing the number every time."
5. Push:
   - `git push -u origin main`
   - Explain: "Push means 'send my commits to GitHub'. The `-u` sets up tracking so next time you can just say `git push`."
6. Have them visit their repo on github.com and see their files.
7. Explain pull:
   - "If someone else (or you from another computer) made changes on GitHub, `git pull` downloads those changes to your computer."
   - Demonstrate by editing a file directly on GitHub's website, then running `git pull` locally.
8. Explain the remote concept: "Your computer is `local`. GitHub is `remote`. Push sends local changes up. Pull brings remote changes down."

## Prompting coaching
- Authentication is often the hardest part. Be patient. If one method doesn't work, try another.
- If they get permission errors, walk through the authentication setup carefully.

## Quiz questions
- What does `git push` do?
- What does `git pull` do?
- What is `origin`?

## Hints (only if stuck)
1. Make sure you're logged into GitHub in your browser first
2. `git remote -v` shows you what remote you're connected to
3. If push fails, it's usually an authentication problem — try `gh auth login`
