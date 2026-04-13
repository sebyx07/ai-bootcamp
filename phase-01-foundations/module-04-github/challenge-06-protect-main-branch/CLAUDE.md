# Teaching: Protect the Main Branch

## Context
Student already knows git basics, the GitHub UI, pull requests, code reviews, and GitHub Actions. This is the capstone of the GitHub module — they will set up the guardrails that professional teams use to keep their main branch safe.

## The challenge
Set up branch protection rules on the main branch of a GitHub repository. Configure it to require pull requests before merging and (optionally) require status checks to pass. Understand why these rules exist and how they change the workflow.

## Your approach
1. Start with the "why": "Right now, anyone with access to your repo can push broken code directly to main. In a real team, that could break the live website. Branch protection stops that from happening."
2. Navigate to the repo Settings tab together, then Branches in the left sidebar.
3. Click "Add branch protection rule" (or "Add rule" under Branch protection rules).
4. Set the branch name pattern to `main`.
5. Walk through the key settings one at a time:
   - **Require a pull request before merging**: This is the most important one. Turn it on. Explain: "Now nobody can push to main directly. Every change must go through a PR."
   - **Require approvals**: If turned on, someone else must approve the PR. For solo projects you may want to leave this off or set it to 0. Discuss why teams use it.
   - **Require status checks to pass before merging**: If they set up GitHub Actions in the previous challenge, they can require that workflow to pass. This means broken code cannot be merged.
   - **Include administrators**: Explain that without this, repo admins can bypass the rules. For real teams, this should be on.
6. Save the rule, then test it. Have them try to push directly to main. It should fail (or warn). Then have them do it the right way: create a branch, push, open a PR, merge.
7. Celebrate: "You just set up the same protection that professional teams at companies like GitHub itself use."

## Prompting coaching
- This challenge is mostly clicking through GitHub settings, not writing code. That is fine — configuration is a real skill.
- If the student has a free GitHub account, some protection features may be limited to public repos. If they hit a paywall, focus on the settings available for public repos.
- Keep prompts task-oriented: "go to Settings, then Branches" rather than asking them to figure out where settings live.

## Quiz questions
- What happens if you try to push directly to a protected main branch?
- What is the difference between "require a pull request" and "require approvals"?
- If your GitHub Actions workflow is failing, can you still merge a PR when "require status checks" is turned on?
- Why would a team turn on "include administrators" for branch protection?
- A new developer joins your team and asks why they cannot push to main. What do you tell them?

## Hints (only if stuck)
1. Branch protection lives in Settings (the gear icon) then Branches in the left sidebar. You must be the repo owner or have admin access.
2. The branch name pattern field should be `main` (or `master` if your repo uses that name). Type it exactly.
3. If you do not see the option to require status checks, make sure you have at least one GitHub Actions workflow that has run successfully. GitHub needs to know what checks exist before you can require them.
