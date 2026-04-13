# Challenge: Auto-Run Tests on Push

## What you'll learn
How to set up a GitHub Actions pipeline that automatically runs your test suite and linter every time you push code.

## Watch first
- [GitHub Actions - Supercharged CI/CD](https://www.youtube.com/watch?v=eB0nUzAI7M8) (12 min) — Revisit the Fireship tutorial, focusing on the test-running sections
- [DevOps CI/CD Explained in 100 Seconds](https://www.youtube.com/watch?v=scEDHsr3APg) (2 min) — Quick refresher on why this matters

## Open Claude Code and say:
> "I'm ready for the challenge"

## You're done when
- [ ] Your GitHub Actions workflow installs project dependencies
- [ ] The workflow runs your linter (ESLint or RuboCop)
- [ ] The workflow runs your test suite (Jest or RSpec)
- [ ] A passing push shows a green checkmark on GitHub
- [ ] You have intentionally pushed a failing test and seen a red X on GitHub
- [ ] You understand how this prevents bugs from reaching production
